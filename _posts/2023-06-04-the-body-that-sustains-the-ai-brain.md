---
layout: post
title: "The body that sustains the AI brain"
date: 2023-06-04
categories: data-plant leadership
---
**TL;DR**: A data plant is the field on which an entrepreneurial AI effort can play out. It is important enough for business to make it a first-order planning goal.

# What is a data plant?
A Data Plant is where the long-term processes involving data can take place:

- Before data is even usable for "AI", it often needs to be augmented with human tags or labels.
- Next, to avoid the "garbage-in-garbage-out" phenomenon, even before any AI work is done, data needs to be thoroughly tested to see that it's making sense (as opposed to: partial, mislabeled, noisy or just not making sense).
- AI per se means training, testing and inference. Each of these business processes happens thousands of times, on different subsets of the same basic data - we'll consider a representative example in the next section.
- After an AI algorithm munches data, it may very well be wrong. Often users will need to curate AI outputs; such curation is fed back either to the AI algorithm directly or to the developers of the AI algorithm to make a better one.

# What business functions does a data plant support?
End-user-bound:
- Data entry (e.g.: media upload, curation/annotation, feedback on AI outputs)
- Piecemeal inference or retrieval of inference results

AI Team-bound:
- Data storage, in bulk for AI-bound data and piecemeal for curation
- Bulk data retrieval for AI testing and training.
- Data analytics for data QA and cleanup.
- Data cataloging and discoverability

# Isn't what you describe a "data platform" or a "tool"?
No, in the same way as a woodworking desk is just one requirement for a workshop and an empty barn is only a part of what it takes to open a warehouse. A hefty amount of iterative business-specific customization is required to make the "can do" into "does do".

Tools like Spark, Databricks, Snowflake, etc. make a lot of complex operations easier and cheaper, but they still require a continuous and determined architectural effort to make sense.

# Garden variety is not enough!
The naive alternative to designing a data plant proactively is letting one grow organically, which means, by the hands of the AI scientists using the data.

However, this approach, which I call the "garden variety data plant" is actually highly hazardous for an organization that wants to succeed. Let me explain why that is the case:

The training of most AI scientists typically lacks two major elements of engineering practice that allow projects to scale up. These elements are:

- Design for operations: Multiple uninspiring but crucial adapters needed to make the plant's work available for other people. A great example of that is making a data entry UI, which is crucial to make tagging and feedback convenient, but is simply out of scope for the vast majority of AI scientists.
- Design for maintenance: the data plant needs to be maintained part-time by other people, to free the AI scientist to do new things. A huge cultural bias here is the fact that most academic AI work discards all code written for a project once it ends - so a lot of scientists have little experience with making a system maintainable in their absence.

# What do you need to do?
Data-centric organizations, in particular AI organizations, need to treat their data plant as a core enabler of their growth. 

*As an organizational leader*, one has to designate a chain of accountability and outcomes appropriate to the organization's ambitions going forward at least a year.

*As an engineering leader*, one needs to ask the hard questions about business: What elements of data architecture are aligned with their organization's realistic needs? When is a product a hyped fad? Is a product appropriate for your organizational scale? What are the implicit assumptions in every path towards fulfilling the data plant product goals? What resources are available for the project? What are the red lines that indicate the project is in trouble? What is to be done in that case? 
