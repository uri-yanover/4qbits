---
layout: post
title: "Tackling 4D Chess"
date: 2022-03-26
categories: blogging career tech-leadership
---
**TL;DR**: How to make good decisions when talent is scarce and expertise even scarcer?

# The peril of non-expert decision making
One of the key obstacles in a team that I've worked with was a certain "stack" of SW that handles the processing of a crucial data source - I should mention that it's not a very complex one, and definitely a very "small" one in terms of data scale.

That SW stack became a festering wound not because somebody specific made a specific bad decision, but rather because several team members had made a number of incremental decisions using high-powered tools somewhat out of their competence zone, and without a holistic vision of the business; these decisions amounted to laying a hefty tax on anyone who would try to base on their work. The end result was not being able to mitigate even trivial data quality issues, which caused the team to fail to deliver on a key business need - in part, because recognizing this need required understanding the system, and that by itself was beyond most team members.

More generally, as business grows, there's a point at which decisions made on an ad-hoc basis by non-experts become the problem - in the typical case they don't allow the right business scaling, and in the worst case they simply break and require a massive cleanup.

It is the organization's vital interest that people making potentially game-changing decisions would do so with preparation, context, support, and would receive feedback to get better the next time around. However it's likely that the need for that won't even appear on the management radar, because none of the people involved realize it's worth flagging! All of that is a recipe for a business disaster.

Further complexity comes from the talent/personnel angle. Whereas in the past there was a decent supply of competent specialists who settled for a single niche field, this is simply no longer the case. Recruiting *anyone* is hard these days, and it is especially hard for positions in which there's no well defined challenge or growth path - in particular, having just one-of-a-kind role in an organization is a very hard sell for most candidates in terms of ability to grow.

# What is 4D chess and who is playing it?
The opposite of the anarchy of non-experts making decisions would be only experts making decisions. However this approach, which I call "centralization" is impossible going forward, period. The reason for that is what I call the attention bottleneck: a modern organization employs such a diverse set of technologies and approaches that having a single decision-maker decide on many categories of these would mean (a) that a single person has to be competent in an unrealistically wide array of subjects and (b) that everybody would need to wait for that person's inputs.

Modern R&D decision-making may be described as "4D chess", where each of the following has long-lasting effects interacting with the other 3:

1. Mission,
2. Choice of platforms and their interfaces,
3. Choice of personnel specializations and growth tracks
4. Choice of work processes, whether formal or not, and investment into tools to support such processes.

Since multiple everyday decisions need to make sense in all 4 dimensions, it is of utmost importance that all decisions are led by the specific team members in need of them; however, to avoid anarchy, social culture and processes must be set up to involve further stakeholders on an ad-hoc basis, and that such decisions are communicated and followed up upon to enable the same stakeholders to make better decisions.

Martin Fowler has a proposal for a specific set of policies to enable such a dynamic in his great piece [Scaling architecture conversationally](https://martinfowler.com/articles/scaling-architecture-conversationally.html). 

# What can go wrong
*Keeping the team out of important decisions*: All decisions involving the team, its various product obligations, its metrics and so on, need to be done in the same framework, or the team will not buy into the method and will typically revert to having a bottleneck somewhere around management.

*The team not fulfilling the culture*: for a team-empowering culture to work, the team needs to act coherently around the principles stated in the previous paragraph, which are definitely not for everyone. Accordingly, team members need to be selected according to the following principles:
Acting out of an understanding that they are the ones to drive processes,
Being able to let other people drive their own processes,
Acting out of an understanding that whatever choices are being made, that would become a part of culture going forward,

*Denying the problem and continuing to rely on formal management*: The most obvious reason for why it's a bad idea is that the decision workload involved is too high to be handled by a single manager, however capable.

The constraints in the above have their own cadence, require focus and dedication, which is incompatible with the "people ops" workload necessary to retain employees in a modern organization.

*Relegating to product managers*: Product managers are not different from people managers - while vision is a central element of product management as a profession, it cannot reach the fateful but routine decisions of the kind described above. In addition, it is even rarer for product managers to have sufficient technological depth for making engineering discussions.

# 4D Chess and people management
Since valid decisions cannot be made by any central authority figure in any case, they need to be delegated into the team - but in a highly principled way; exactly as it currently a common expectation from developers to perform quality control of the work they're carrying out, it should be a common expectation today they perform a proactive and informed design process, and as a part of that, reach out to impacted stakeholders.

A system in which crucial decisions are made at the ground floor is incompatible with the common tier-0.5 ("tech lead") and tier-1 ("person who decides for you") management styles.

The core attributes required from managers in this model had formerly been associated with tier-2 management:
- Cultural awareness and insistence on team dynamics,
- Establishment of robust and useful communication channels,
- Deliberate and consistent delegation of technical decisions; staying out of the loop
- Extreme attention to sources of friction in team operation and to the envelope: costs, staffing, tooling/automation, tracking dependencies and so on.

The above runs against one core attribute of the incumbent tier-2 management population: it does not involve a massive headcount, which is often used as a career metric by management. It is accordingly crucial that the organizational management style centralizes the quality of outcomes and the efficacy of leadership and treats headcount as just an incidental aspect of growth.

# Summary
Modern SW is defined by an abundance of shortcuts that make it possible to achieve great outcomes using a small team - provided that they act right. If they act wrong, they may just achieve the wrong outcomes or set out to a tedious track not arriving anywhere business-like. The way to keep that from happening is for the entire organization to stick by a certain decision-making culture that rejects centralization at all costs and empowers decision-making through each individual playing 4D chess.

As with all non-trivial cultural choices, this one puts a burden on the organization as a whole, by selecting only such team members that can do good by this culture, and by keeping them informed and guiding their everyday routine to align with such culture. However if done correctly, the end results may be transformative. Indeed, one may not need to look further than WhatsApp that supported 400M users with 35 people, or Telegram that built a business empire with a few hundred people at most. 

So to sum up - we live at an age in which working hands on deck working smart are the true bottleneck – we should better act like it.

