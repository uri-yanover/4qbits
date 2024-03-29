---
layout: post
title: "Tackling 4D Chess"
date: 2022-03-26
categories: blogging career tech-leadership
---
**TL;DR**: How to make good decisions when talent is scarce and expertise even scarcer?

# Note (added April 18th, 2022)
A lot of people like starting with [a specific example of the 4D technical decision analysis paradidm]({% link _posts/2022-04-16-a-fateful-full-stack-decision.md %}). This post deals with the question - what kinds of culture/leadership mentality are necessary to apply this paradigm successfully.

# The peril of non-expert decision making
One of the key obstacles in a team that I've worked with was a certain "stack" of SW that handles the processing of a crucial data source - I should mention that the data per se is not very complex, and definitely very "small-scale" as far as these things go.

That SW stack became a festering wound not because somebody specific made a specific bad decision, but rather because several team members had made a number of incremental decisions using high-powered tools somewhat out of their competence zone, and without a holistic vision of the business; these decisions amounted to laying a hefty tax on anyone who would try to base on their work. The end result was not being able to mitigate even trivial data quality issues, which caused the team to fail to deliver on a key business need - in part, because the system became too complicated for anyone to feel accountable for.

More generally, as business grows, there's a point at which decisions made on an ad-hoc basis by non-experts become the problem - in the typical case they don't allow the right business scaling, and in the worst case they simply break and require a massive cleanup.

It is the organization's vital interest that people making potentially game-changing decisions would do so with preparation, context, support, and would receive feedback to get better the next time around. However it's likely that the need for that won't even appear on the management radar, because none of the people involved realize it's worth flagging! All of that is a recipe for a business disaster.

Further complexity comes from the talent/personnel angle. Whereas in the past there was a decent supply of competent specialists who settled for a single niche field, this is simply no longer the case. Recruiting *anyone* is hard these days, and it is especially hard for niche or organization-proprietary technologies, for which there's no well defined challenge or growth path.

# What is the "4D chess" and who is playing it?
The opposite of the anarchy of non-experts making decisions would be only experts making decisions. However this approach, which I call "centralization" is simply impossible going forward. The reason for that is what I call the *competence bottleneck*: a modern organization employs such a diverse set of technologies and approaches that having a single decision-maker decide on many categories of these would mean (a) that a single person has to be competent in an unrealistically wide array of subjects and (b) that the entire team would need to wait for that person's inputs.

Modern R&D decision-making may be described as "4D chess", where each of the following has long-lasting effects interacting with the other 3:

1. Mission (current and foreseeable);
2. Choice of platforms and their interrelations (platforms being defined as technological choices affecting more than a single mission);
3. Choice of personnel specializations and growth tracks;
4. Choice of work processes, whether formal or not, and investment into tools to support such processes.

Since multiple everyday decisions need to make sense in all 4 dimensions, it is of utmost importance that all decisions are led by the specific team members in need of them; however, to avoid anarchy, social culture and processes must be set up to involve further stakeholders on an ad-hoc basis, and that such decisions are communicated and followed up upon to enable the same stakeholders to make better decisions.

Martin Fowler has a proposal for a specific set of policies to enable such a dynamic in his great piece [Scaling architecture conversationally](https://martinfowler.com/articles/scaling-architecture-conversationally.html). 

# What can go wrong
*Denying the problem and continuing to rely on formal management*: The most obvious reason for why it's a bad idea is that the decision workload involved is too high to be handled by a single manager, however capable.

The constraints in the above have their own cadence, require focus and dedication, which is incompatible with the "people ops" workload necessary to retain employees in a modern organization.

*Relegating to product managers*: Product managers are not different from people managers - while vision is a central element of product management as a profession, it cannot reach the fateful but routine decisions of the kind described above. In addition, it is even rarer for product managers to have sufficient technological depth for making engineering discussions.

*Organization only relies on the team for some decisions*: All decisions involving the team, its various product obligations, its metrics and so on, need to be done in the same framework, or the team will not buy into the method and will typically default to having management decide, which will reintroduce the bottlenecks of a manager-centric culture.

*The team not buying into the culture*: for a team-empowering culture to work, the team needs to act coherently around the principles stated in the previous paragraph, which are definitely not for everyone. Accordingly, team members need to be selected for being able to:
- Exercise personal accountability for driving decisions accross the 4D space;
- Supporting other people driving their own processes;
- Make everyday choices while considering the cultural consequences of each such choice.

# 4D Chess and people management
Since valid decisions cannot be made by any central authority figure in any case, they need to be delegated into the team - but in a highly principled way; exactly as it currently a common expectation from developers to perform quality control of the work they're carrying out, it should be a common expectation today they perform a proactive and informed design process, and as a part of that, reach out to impacted stakeholders.

A system in which crucial decisions are made at the ground floor is incompatible with the common tier-0.5 ("tech lead") and tier-1 ("person who decides for you") management styles.

The core attributes behaviors from managers in this model are inherent in [trusting employes with major business outcomes]({% link _posts/2022-02-20-on-positions-of-trust-part-ii-what-about-you.md %}); accordingly, a lot of these are have historically been considered the realm of tier≥2 management:
- Focus on culture and team dynamics;
- Establishment of robust and useful communication channels;
- Deliberate and consistent delegation of technical decisions; avoiding blocking decision paths in all but extraordinary circumstances;
- Devoting extreme attention to risks and sources of friction in team operation and to the envelope: costs, staffing, tooling/automation, tracking dependencies and so on.

Focusing on high execution quality runs against one core aspect of the incumbent tier≥2 management population: quality comes at the expense of quantity - in this case, of team size, which is used as a career metric by many individuals. It is accordingly crucial that the organization sets expetations at large regarding the quality of leadership, while treating headcount as an incidental aspect of growth.

# Summary
Modern SW is defined by an abundance of shortcuts that make it possible to achieve great outcomes using a small team - provided that they act right. If they act wrong, they may just achieve the wrong outcomes or set out to a tedious track not arriving anywhere business-like. The way to keep that from happening is for the entire organization to stick by a certain decision-making culture that rejects centralization at all costs and empowers decision-making through each individual playing 4D chess.

As with all non-trivial cultural choices, this one puts a burden on the organization as a whole, by selecting only such team members that can do good by this culture, and by keeping them informed and guiding their everyday routine to align with such culture. However if done correctly, the end results may be transformative. Indeed, one may not need to look further than WhatsApp that supported 400M users with 35 people, or Telegram that built a business empire with a few hundred people at most. 

So to sum up - we live at an age in which working hands on deck working smart are the true bottleneck – we should better act like it.

