---
layout: post
title: "GitHub Actions as a data leak vector"
date: 2022-04-03
categories: blogging security systems
---
**TL:DR**: The GitHub Actions (GHA) security model is broken, and in many cases may allow escalating an "ordinary developer" level of access into obtaining infrastructure credentials sufficient to inject malicious artifacts into trusted repositories

# Statement of problem
GitHub is a popular platform for storing source code. To be usable, source code is "built" into artifacts, such as ".exe" binaries for Windows, container images, packaged libraries such as JARs in Java and more. GitHub Actions (GHA) are a powerful tool used for orchestrating the preparation of artifact out of the sourcre code and conducting quality control over these artifacts.

Typically, after a build succeed, it is is *enlisted* into a repository, which means taking the prepared artifacts and copies them for long-term storage into an external *artifact repository*, such as Artifactory, PyPi, NPM and so on. The GHA method for authenticating to an external repository is by keeping the necessary credentials in a special piece of GHA configuration called a "secret". 

Major damage is likely to ensure if malicious actors are able to enlist artifacts. As an example, if an artifact in question is a web service that processes payments, a malicious actor can hijack the normal flow so that it leaks payment method data.

While GitHub maintains the optics that only a handful of repository administrators can access secrets, I will show that in many configurations GHA secrets can in fact be extracted by any user with commit rights to a repository - which adds up to a major and often unanticipated attack surface.

# What are GitHub Actions and how are they used?
GitHub Actions (GHA) is a popular CI automation framework. Simply put, it is a set of hooks that cause scripted actions to be executed at specific steps in an organization's source control processes. 

Several representative kinds of actions are:
- Running automated test suites - to validate that newly committed code did not introduce regressions.
- "Building" - transforming code into a consumable format; for example compiling Java source files into a JAR deliverable
- "Listing" - copying build artifacts into an artifact repository.

Unlike other actions, "listing" means GHA has to make a permanent change external to the GitHub platform. Moreover, culturally, once an artifact had been listed, it's considered "trusted enough for use by the intended audience", and in particular - not having been tampered with.

And now for the clash: the boilerplate GHA way for listing artifacts is inherently insecure!

# Constructing a malicious action
**For several commonly used repository types, the GitHub security model allows arbitrary code in the repository to unconditionally access any secret configured for GHA.**

There are two major malicious behaviors a GitHub action could do:
- It could leak a service account key (for example, by printing it out into the logs in an obfuscated manner)
- It could list an artifact that would not have been listed otherwise; in some cases it might even overwrite an earlier, legitimate, artifact.

All it takes to execute a malicious action is:
1. To register one commit containing the code for such an action,
2. To register another commit requesting the use of the action in the first commit.

By design, these steps only require commit privileges. The only restrictions that GitHub imposes is that some people with commit rights are not allowed to commit into "important" branches, such as "master". However the steps above do not assume being in such a branch, and actions are executed regardless of branch.

# GitHub is aware that this is fishy - why doesn't it create better controls?
GitHub's take on the described weakness is twofold. One one hand:
-  the [GHA hardening documentation](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions) mentions  the possibility of credential exfiltration; accordingly it is apparent that at least the security review team at GitHub is aware of the major damage potential. (I conjecture the docs are an attempt to clear GitHub's public conscience on the matter)
- GitHub UI tries to treat secrets as restricted to admins only. 
- GitHub detects and removes inadvertent printouts of secret contents from build logs.

However on the other hand, GitHub only provides a single feature to allow de-facto secret governance, and that feature is not available to the generality of GitHub users. The feature is ["Environment Secrets"](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment), and it introduces a specific kind of secrets that are only accessible after the code in question underwent a review. This feature is only available to public repositories and to Enterprise clients; using environment secrets is optional, and same users are also allowed to use the "regular", weak, secrets. Also, while requiring actions of two users to enable the use of a secret is a stronger guarantee than having just one, it could still be seen as too lax.

A better option would have been for GitHub to let repository administrators specify in a fine-grained way which actions are allowed in that repository. However as of now (April 3rd, 2022), GitHub only provides a coarse control over that - the options right now are:
- Disabling all actions
- Allowing all actions
- Allow only actions from the same organization/user
- Allow only actions from the same organization/user, plus an allow-list

Since all options except an outright disable allow usage of an arbitrary action from the current repo, their existence does little to improve security.

# Summary
Distributed source control and GitHub in particular removed an enormous amount of complexity from code development, by empowering any developer in an organization to easily commit their code into a low-cost, low-friction source code management system.

However the weakness of the GHA security model means that every developer can cause arbitrary artifacts to be listed. Should a developer's credentials fall into malicious hands, there's absolutely nothing preventing the introduction of malware into a trusted artifact repository. Moreover, if the artifact repository allows overwriting existing artifacts, the same weakness would allow replacing a previously-secure artifact with an insecure one!

**It is my hope that going forward GitHub would introduce fine grained control over access to GHA Secrets; even easy measures like restricting only to authorized branches and to authorized actions will likely be highly beneficial for addressing the issue described in this post.
Until GitHub refines the GHA security model, it is my recommendation to:**
- **Avoid using GHA for directly listing artifacts into repositories**
- **More generally, regard any permission granted to GHA as having been given to everyone who can commit to the repository**

However, even in the current, flawed, model one can still use GitHub Actions securely as an indirect trigger - one could use an Action to launch an automation off-GitHub, that can perform its own set of validations in a way that GitHub currently does not allow. Such a script could for example validate that only an explicitly approved branch may be used as a basis of an artifact being listed in a trusted artifact repository.

# Credits
I would like to thank Max Held for raising the question of GHA security and Gil Dabah for his invaluable help writing this post.
