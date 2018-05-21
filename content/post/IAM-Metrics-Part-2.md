---
date: "2018-05-21T16:05:01-05:00"
title: "IAM Metrics Part 2 - Improving How We Do Business Now"
authors: []
categories:
  - IAM
  - Enterprise
tags:
  - metrics
cover: /images/metrics-2.jpg
draft: false
---
***It can be difficult to know what to measure at which stage of your IAM implementation.***

In case you missed it, [in Part 1 we talked about some IAM metrics you can use to measure Deployment Success and Risk Reduction.](http://mattkopecki.com/post/iam-metrics/) 
It makes a lot of sense to start there because it's easy to see how IAM is providing tangible benefits to your organization even before it's mature enough to noticeably affect your team's day-to-day operations.

Pretty shortly thereafter, though, the IAM system *will* start improving day-to-day operations. This is a crucial benefit of an IAM system, and these performance improvements were probably some of the main selling points of your recent IAM modernization projects. If they were, it's especially important that you circle back, measure, and report on the improvement in these areas.

In case you haven't yet been too specific before about what operation improvements your organization could expect to see from an IAM system, now is a great time to get more specific by using the metrics listed below.

#### How To Execute

These **performance metrics** are relatively interesting on their own, but finding and linking to relevant Key Performance Indicators (KPIs) will always be better than reporting IAM metrics in a vacuum.

If your IAM team hasn't already defined KPIs, reach out to adjacent/affected areas of the business to see what your stakeholders may have defined. IAM metrics often show operational changes in the day-to-day of IT Operations, HR Technology, helpdesk teams, compliance & audit organizations, and individual application & system owners.

* **Efficiency Metrics:** How is the IAM system helping the IT and adjacent organizations do their jobs more efficiently? 
  - _Number of calls to password help desk_
  - _Password reset volume per month_
  - _Average time it takes to authorize a change_
  - _hint:_ these last two efficiency gains also represent a shift in the way the business runs overall. Part 3 of this series will have more metrics like these!
  - _Administrative leverage delivered by roles_
  - _Percent of access-related transactions fulfilled via policies instead of access requests_
* **Effectiveness Metrics:** How is the IAM system enhancing data quality across the enterprise? Better data quality translates directly into lower risk in multiple dimensions. 
  - _Active identities with missing/multiple source records_
  - _Terminated employees with active accounts_ - Remediate these ASAP!
  - _Contractor accounts with invalid expiration date_
  - _Identities with invalid supervisor_
  - _Dormant accounts_
  - _Never-logged-on accounts_
  - _Remediation of orphan/rogue accounts:_ - Timeliness, Outcomes (e.g., classification, owner assignment, removal).
  - _Access certification metrics:_ - Uncertified request-based assignments, Uncertified privileged accounts.
  - _Too-rapid attestations_ - these usually signal "rubber stamping" of certifications. Rubber stamped certifications aren't effective certifications
  - _Segregation of duties (SOD) risks:_ - report on active SOD risks (those with and without mitigating controls), and the timeliness of remediation (broken out by risk level).
  - _Number/Severity of audit findings_
* **Enablement Metrics:** How is the IAM system improving user experience, and how does that improved user experience allow people to do better work?
  - _Employee, developer and customer satisfaction survey results._
  - _Time spent using the system_ - How quickly can someone find and request access? How long does it take to complete a certification?
  - _Ease of onboarding new users_
  - _Additional reach of SSO solutions_
  - _Account/Application usage_ - Why are we paying for licenses for people who aren't using them? Why do some people have multiple seats? Maybe we should adjust our licensing agreements.

This isn't intended to be a comprehensive list of all IAM metrics, but hopefully demonstrates how you can (and why you should) incorporate metrics into your IAM deployment at various stages of maturity.

In the end, these metrics really aren't rocket science. They mostly consist of taking anything you can measure and comparing it per month or per user! This can be more instructive than just looking at raw counts, so get creative about other things you can measure in your specific deployment scenario.