---
layout: post
title: "Choosing a technology as a decision on The Team You're Gonna Have"
date: 2022-03-05
categories: blogging career
---
**TL;DR**: Choosing a technology is really a statement about future organizational culture and structure.

# "Should we be using that tool?"
A few months ago I was asked if a certain team should be using a certain tool (specifically: [dbt](https://www.getdbt.com/) -- but that's not actually important for the rest of this post).

I did some research, and realized that the tool in question was built for solving a certain class of business problems ("creating maintainable ETLs") for an organization that has a supply of people with a specific skill set ("business analysts who only know SQL"). The business problem in question inherently involves a great deal of incremental maintenance over time, and accordingly adopting the tool for use by the team would mean having team members specialize in that relevant skill set as well as the tool itself.

Then I talked to a few folks and discovered was that acquiring and honing the skill-set in question would have been considered a career distraction for most team members. Accordingly, my recommendation was to use a different technology that capitalized on the team's existing knowledge base, perhaps at the cost of decreased elegance or having to toil a bit more.

# Several further examples
1. Kubernetes (k8s) is a great demonstration of how a tool can define a team. The mental model k8s uses to describe production IT systems is so complex that it "requires a Ph.D." Accordingly, the choice to transition DevOps to use k8s means accepting the fact that k8s will become *the* defining skill for the entire DevOps team, and that such a transition will require a significant mindshare in terms of how the team recruits people, trains them and which best practices it monitors and enforces.

2. [testim.io](https://www.testim.io/) is a great no-code testing platform for web applications. However it implicitly assumes that either the application doesn't have CI/CD at all, or that there is a more complex CI/CD pipeline that integrates with testim.io.

3. Google Data Studio and Kibana are great low-code/no-code data dashboarding applications. However they both need a data ingestion and transformation process (ETL) creating a CSV data dump, or perhaps some tailored SQL or BigQuery queries to get the raw version of the data into the dashboard.

We can generalize the last two bullets by saying that Low-code/No-code platforms are useful if and only if there's a mostly-non-SW team that can use them in a self-serve manner, with the SW/DevOps people working on the infrastructure to make them tick.

# How to go about such choices?
My central thesis is that the technical culture is an integral part of overall organizational culture; as engineers, we need to analyze and proactively decide as holistically as we can.

Choosing tools is a balance between multiple types of considerations:
1. Up front resource investment before a solution can be validated;
2. Resource investment necessary for scaling - scaling parameters could be adding new functionality, increasing business volume, etc.;
3. Quality of supplied service, in particular seen through the prism of the organizational velocity it unlocks (e.g., through superior development experience);
4. Resources necessary to maintain outcomes "at rest" (for example: making sure the platform does not fail for business)
5. Current and aspirational team specializations - with the understanding that adding a major new discipline comes at the expense of excellence in other disciplines, that some skill sets are considered much "better" than others in terms of career growth.

The best we can do is to consider the relevant angles out of the above, to make an informed and proactive decision and to follow up later and see if it made sense.

After 15 years of doing that, it still amazes me how several weeks of scoping work done with the right questions can save you months of timeline and person-years of investment going the wrong way. If you feel you'd like to learn from me how to do it – I'd be more than happy to mentor you; as with all mentoring I do - I do it voluntarily, for free and without any strings attached.
