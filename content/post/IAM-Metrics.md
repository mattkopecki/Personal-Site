---
date: "2018-04-20T14:05:01-05:00"
title: "IAM Metrics - Part 1"
authors: []
categories:
  - IAM
tags:
  - metrics
draft: true
---
What do I measure and how do I tie that to business outcomes?
What should you measure, how should you use that info, how should you prioritize what to measure

later on, it can be assumed that you're playing with a full deck and all your accounts etc. are covered. until you can make that 100% assumption though, it's useful to measure that percentage.

Even after you get to 100%, counts are useful to illustrate growth, and then will also start to become inputs into more targeted metrics (average count per time or average count per user)

Category: coverage --> deployment success, but also tied to risk reduction. Maybe link to KRIs, and link to other performance indicators
* Account and Repository Coverage
  - These are simple metrics:
    + Account repository coverage
    + Total account coverage
  - Some advantage in categorizing account repositories:
    + Sensitivity (e.g., regulatory significance, risk, supply chain)
    + Applications versus infrastructure
  - Highlight growth in repositories
* Authentication Coverage
  - Authentication methods allocated to endpoints:
    + User experience advantages for integration
    + Risk reduction with some authentication types
    + Mobile and multifactor authentication could be factored in
  - Some advantage in categorizing authentication endpoints
* Privileged Access Management Coverage
  - Prioritization of coverage based on account types:
    + Shared accounts with high privileges (system, operational) present highest risks usually
  - May be opportunities for further granularity:
    + Service accounts
    + Application-to-application accounts


Number of reconciliation exceptions
Separation of duty violations

uncorrelated accounts
