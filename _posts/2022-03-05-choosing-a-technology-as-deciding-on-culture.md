---
layout: post
title: "Choosing a technology as a decision on The Team You're Gonna Have"
date: 2022-03-05
categories: blogging career
---
**TL;DR**: Choosing a technology is really a statement about future organizational culture and structure.

"Should we use that tool?"
A few months ago I was asked if an organization should be using a certain tool ([dbt](https://www.getdbt.com/), but that's not the point).

I read about it a bit, and realized the following: the tool is something that allows you to solve a certain class of business problems ("creating maintainable ETLs") under the assumption that the organization in question has a supply of people with a specific skill structure ("business analysts who only know SQL"). 

The business problem in question implies a great deal of incremental maintenance, and accordingly accepting it into the team would mean having team members specialize in the relevant skill set. What I discovered was that SQL was not something the team wanted to specialize in. Accordingly, my rcommendation was to use a different technology that did not involve a major skill shift.

# Several examples
1. [testim.io](https://www.testim.io/) is a great no-code testing platform for web applications. However, for there being something to test, there needs to be a CI/CD pipeline that deploys test versions of the web app in a way that's accessible to the platform
2. Google Data Studio and Kibana are great low-code/no-code data dashboarding applications. However they both need a data ingestion and transformation process (ETL) or perhaps some tailored SQL or BigQuery queries to get the raw version of the data into the dashboard.

   We can generalize the above two points by saying that Low-code/No-code platforms if and only if there's a non-technical team that can use them in a self-serve manner, with the technical team providing the platforms.

3. k8s is a notorious example for a similar idea: the set of ideas needed to properly specify a production IT system is so complex that it "requires a Ph.D." Accordingly, when one prepares to transition their devops to k8s, they need to accept the fact that it will become the defining skill for their DevOps team, and that it will require a significant mindshare in terms of how the team recruits people, trains them and which best practices it monitors and enforces.

# What to do about choosing technical infra?
My central thesis is that the human culture is an integral part of overall organizational culture; as engineers, we need to analyze and proactively decide as holistically as we can.

Choosing tools is a balance between multiple types of considerations:
1. Cost/time/implications of achieving the outcome until we can validate the solution;
2. Cost/time/implications of scaling the outcome - scaling parameters could be adding new functionality, adding business, etc.;
3. Quality of infrastructure, in particular of the development experience,;
4. Cost/time/implications of continuously maintaining the outcome (for example: supporting an external analysts team)
5. Current and aspirational team specialization - with the understanding that adding a major new discipline comes at the expense of professionalism in other disciplines, that some skill sets are considered much "better" than others in terms of career growth.

The best we can do is to consider the relevant angles out of the above, to make an informed and proactive decision and to follow up later and see if it made sense.

After 15 years of doing that, it still amazes me how several weeks of scoping work done with the right questions can save you months of timeline and person-years of investment going the wrong way. If you feel you'd like to learn from me how to do it – I'd be more than happy to mentor you; as with all mentoring I do - I do it voluntarily, for free and without any strings attached.
