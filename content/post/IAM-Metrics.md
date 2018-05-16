---
date: "2018-04-20T14:05:01-05:00"
title: "IAM Metrics - Part 1"
authors: []
categories:
  - IAM
  - Enterprise
tags:
  - metrics
draft: false
---
# Preface - Should We Measure?

While there certainly is some value in listing and examining some of the top IAM metrics, as might be found in other resources, it can be difficult to know what to measure at which stage of your IAM implementation. 

Would it be great if you started measuring the average time to detect and resolve a native change across each connected target system? Of course! But before you can do that, you would need a mature enough IAM ecosystem where all targets were connected, no out-of-band provisioning was to be occuring, and you had a dedicated team who monitored and responded to out-of-band changes as soon as they were alerted that changes were made directly in the targets. For most enterprises, those are lofty goals.

So should you wait to start measuring your IAM program until later? No, there is plenty of business value to be gained from implementing IAM metrics as soon as possible. As your IAM environment matures it generally makes sense to carve out project time to specifically define and implement IAM metrics, but for now, here are some things to focus on while you execute the early phases of a deployment.

This series isn't intended to create a comprehensive list of all IAM metrics, but will aim to at least lay a cohesive framework for how you can (and why you should) incorporate metrics into you IAM deployment at various stages of maturity.

# Where Do We Start?
*What do I measure and how do I tie that to business outcomes?*

Keep things simple to start. You have a lot going on just making sure the deployment is a success. And in fact, with a few simple metrics you can start measuring the success of the deployment.

Begin with **coverage metrics** that show the reach of your IAM program. Later on, you'll be able to assume that you're playing with a full deck and all your users, accounts, in-scope target systems, etc. are covered by your IAM system. Until you can make that 100%-coverage assumption though, it's useful to measure those percentages.

Even after you get to 100%, counts will continue to be useful to illustrate growth, and then will also start to become inputs into more targeted metrics (average count per time, average count per user...). Starting with these coverage metrics is both immediately useful and lays good groundwork for the future.

In addition to illustrating deployment success, coverage metrics can also be tied to risk reduction outcomes with minimal additional work. Most organizations already have key risk indicators (KRIs) in place for their security programs (if not, here's the part where it will take some work to define them). With a little documentation and communication, IAM coverage metrics can easily be tied to existing KRIs. Note also that KRIs are usually relatively static, as compared to KPIs which frequently deal with the performance of some system or process over time. Stay tuned for more on KPIs next time.

# How To Execute

Each IAM implementation will have slightly different user types, accounts, and targets in scope, but here's an example list to get you started.

* **Account and Repository Coverage** - these metrics show IAM deployment success when linked to a percentage of completion of project scope, and show risk reduction when linked to KRIs around Data Management Risk or Technology Vendor/Third-Party Risk. If defined, any KRIs around IT Program Execution Risk are also easily supported by coverage metrics like these.
  - Total account coverage
  - Account repository coverage. Potentially advantageous to categorize account repositories, maybe by Sensitivity (e.g., regulatory significance, risk, supply chain) or by Type (Applications versus infrastructure)
  - Number of uncorrelated accounts
  - Highlight growth in repositories
* **Authentication Coverage** - easy to tie to risk reduction when comparing the security provided by different authentication methods. Less tangibly, you might be able to measure user experience advantages by authentication method. If defined, look for KRIs around IT Resiliency and Continuity Risk to tie to.
  - SSO passthrough volume
  - Failed authentication attempts
  - Mobile and multifactor authentication could be factored in or broken out separately. And again, it could potentially be advatageous to categorize your metrics by authentication endpoint
* **Privileged Access Management Coverage** - security professionals understand the importance of privileged credentials in any cyber threat model, and should look for KRIs in Cyber Security and Incident Response Risk domains. Other than total account coverage, PAM coverage can be one of the headline metrics for demonstrating deployment success.
  - Prioritization of coverage based on account types:
    + Shared accounts with high privileges (system, operational) present highest risks usually
  - May be opportunities for further granularity:
    + Service accounts
    + Application-to-application accounts
* **Counts of IAM Events** - if you have an IAM system in production, you'll be generating some type of event logs. Without needing to get into detail on *how* these events were generated or resolved, it can still be useful to track pure volumes
  - Number of approvals solicited by the IAM system
  - Number of resources provisioned
  - Number of reconciliation exceptions
  - Number of Separation of Duty violations

***Key Execution Detail:*** make sure you have at least *some* reporting requirements in your first IAM system release. Almost all packages come with some reports out-of-the-box, but you might be surprised what you *can’t get* without some customization. Make sure you've at least seen the list of OOTB reports, and hopefully even seen an example of each. A little foresight goes a long way towards making sure you have the right building blocks available from the get-go. However, don’t be afraid to combine reports outside of the IAM tool (e.g. in Excel) to get what you need. If you can get reports by identity, account, and target, you can get a long way with VLOOKUPs.

  - Example: Report listing Authoritative Identites + Report of Accounts by Identity = all accounts from a specific target which are linked to a human identity || identities with multiple accounts in a target || accounts without an authoritative identity || etc.
