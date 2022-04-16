---
layout: post
title: "A fateful decision on choosing a SW stack - in 4D"
date: 2022-04-16
categories: blogging leadership software
---
**TL;DR**: A walkthrough of how to make the right choice of a SW stack for a project

In [my previous post]({% link _posts/2022-03-26-tackling-4d-chess.md %}), I presented the following four crucial dimensions of consequences of technical decision-making:

1. Mission (current and foreseeable);
2. Choice of platforms and their interrelations (platforms being defined as technological choices affecting more than a single mission);
3. Choice of personnel specializations and growth tracks;
4. Choice of work processes, whether formal or not, and investment into tools to support such processes.

Let's now examine a specific decision in that framework and see what we arrive at.

# Problem statement
A specific operation that's performed once a week requires the entry and occasional editing by a non-technical employee of a record containing about 3 layers of data nesting. Which SW infrastructure should be used to underlie this rather mundane process?

# Solution Space
The problem calls for a user-facing "front-end" piece, a data-serving "back-end" piece and for glue to connect them together. As with most production systems, feature work, validation, bug fixes and deploy work are going to be a source of considerable operational friction.

One "best practice" approach to this problem is to cast the problem into the domain of modern web apps; they require a front-end, perhaps React-based and a back-end, for which some fashionable choices are e.g. Node JS, perhaps running on Heroku. Let's call this a "blank-slate" approach.

However for the typical case of a small, overloaded, SW engineering team, we should also consider a low-code/no-code application server. Some examples are:
- ASP.net (FE+BE "single-moving-piece")
- Retool for FE and Serverless (AWS Lambda or Google Cloud Functions) for BE,
- [schema-editor](https://json-editor.github.io/json-editor/form-submission.html) FE and Serverless (AWS Lambda or Google Cloud Functions) for BE
- Python [WTForms](https://wtforms.readthedocs.io/en/3.0.x/) (for a genuine FE+BE single-moving-piece, but hard to customize)
- A radical solution: using an online spreadsheet like Google Sheets, possibly with some automation using Google Apps Script (pushes the BE part to other places in the system).

# Analysis
The substantial difference between solution architectures is their "scaling curves"; all platforms require some kinds of up-front investment to get anything out all and some kind of incremental investment to support more complex features as they come along.

The guiding pattern of thought when comparing these sub-options is – how much work overall is the team expected to carry out during the next year? If it's "a lot", we should aim for the overall lowest development cost per feature; if it's "one", we need to select the platform with the lowest onboarding cost. If we're unsure, we should focus on a low-cost one-off and postpone making a longer-term decision in an agreed-upon way.

Let's analyze the implications according to the 4 dimensions:
1. All of the listed solutions serve the stated *Mission*, although there's a difference between a "blank-slate" application as opposed to the "opinionated" frameworks: the "blank-slate" approach allows absolute freedom at the cost of much greater complexity. This freedom is only useful if we foresee use cases that cannot be reasonably supported by the framework.
2. *Choice of platforms and their interrelations*: since platform onboarding always comes at a major cost, we really should minimize the amount of platforms we're using. Another source of cost is complexity; solutions with the least moving pieces are the least complex. This perspective favors the single-moving-piece WTForms to the "choreographing a Broadway show" complexity of starting with Retool.
3. *Choice of personnel specializations and growth tracks*: for main-track engineers, "Blank-slate" seems to be very popular, opinionated infra tends to be unpopular and office app automation is an anathema. While we should only consider options that would not be toxic to team morale, the team should also feel accountable if they choose an uneconomical solution just for bragging rights.
4. *Choice of work processes*, whether formal or not, and investment into tools to support such processes: depending on the platform, this might be a major source of friction. In particular, blank-slate would often allow better end-to-end QA automation, but at the expense of having to build from scratch. Retool and ASP.net require a major investment in deploying an application server, having a DB that it would talk to, etc.

# Resolution
The optimal choice in the dilemma described above is highly dependent on the specifics of the team and on the workload in general.

For the specific case of the team I was involved in, which is under a highly sporadic workload, my sympathy lies with the "fewest moving parts" philosophy, which inclines towards "enriched back-ends" solutions such as WTForms or a plain Flask/Node back-end with a static schema-editor front-end.

However, the above choice could come to be problematic, or even catastrophical, depending on what happens down the road. One example would be if there was suddenly a need to implement a multi-step UX flow that would exceed the very basic capabilities provided by such simple tools. 

An even greater peril would be if the inevitable downsides in the chosen tools were to silently block for new impactful work - a complex but rarely used stack would become "too complex to touch", which would mean that even minor changes would become impossible, to the overall detriment of the business.

Accordingly, it is crucial to revisit decisions of this kind within a few months' time and see if their fundamental assumptions still hold; at least for me, the above 4 Dimensions is a good way of going about that.
