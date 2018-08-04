---
date: "2018-07-31T14:05:01-05:00"
title: "IAM Metrics Part 4 - Measuring Customer Effectiveness"
authors: []
categories:
  - IAM
  - Enterprise
tags:
  - metrics
cover: /images/metrics-4.jpg
draft: false
---

Whether you have a full CIAM solution in place, or maybe just some reporting out of a federated identity store, if your IAM solution has non-employee identities of any sort then there are a few interesting things you can start to measure.

Some of these sound fancy, but still aren’t anything like what you’d get in the ad industry. Those thypes of companies have whole identity programs too, but they’re very different than your standard enterprise identity program. Instead of authoritative stores of users, they have browser fingerprints, cookie tracking, and analytics. There’s a lot to learn from them, but what follows are examples of some things you can do with existing standard enterprise technology.

#### How To Execute

**B2B Interactions** - business customers are one example, but these metrics also make a lot of sense when applied to accounts issued to vendors, suppliers, and third party contractors.

- *B2B accounts with invalid expiration date*
- *B2B accounts with invalid business partner*
- *B2B accounts with invalid sponsor*
- *Consumer identities unmatched in CRM*



**B2C Interactions** - when you can tie application events and business processes to identity data, you can build interesting metrics that folks outside of the security organization would love to get their hands on.

- Customer Enrollments:
  + *Account creation*
  + *Subscriptions and profiles*
  + *Guest interactions*
  + *Social logins*
- Repeat Access:
  + *Frequency of visits*
  + *Associated purchases*
- Cross-Selling:
  + *Interest in/attraction to other offerings*
- Dormancy:
  + *Registration abandonment*
  + *Cart abandonment*
  + *Accounts not accessed*
  + *Account expiration*
  + *Lost IDs and forgotten passwords*