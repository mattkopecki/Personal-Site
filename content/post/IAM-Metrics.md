---
date: "2018-05-15T14:05:01-05:00"
title: "IAM Metrics Part 1 - Measuring Deployment Success and Risk Reduction"
authors: []
categories:
  - IAM
  - Enterprise
tags:
  - metrics
draft: false
---
#### Preface - Should We Measure?

Of course it would be great if you started measuring something fancy like _the average time to detect and resolve a native change across each connected target system_. But before you can do that, you would need your IAM ecosystem to be mature enough that all connected targets were fully automated so no out-of-band provisioning was to be occurring, and you would need a dedicated team who monitored and responded to out-of-band changes. For most enterprises, those are lofty goals.

So should you wait to start measuring your IAM program until later when it's more mature? No! There is plenty of business value to be gained from implementing IAM metrics as soon as possible. Later on, as your IAM environment matures, it generally makes sense to carve out project time to specifically define and implement IAM metrics. For now, here are some things to focus on while you execute the early phases of a deployment.

This series isn't intended to create a comprehensive list of all IAM metrics, but will aim to at least lay a cohesive framework for how you can (and why you should) incorporate metrics into you IAM deployment at various stages of maturity.


#### Where Do We Start?
*What do I measure and how do I tie that to business outcomes?*

It can be difficult to know what to measure at which stage of your IAM implementation.

Keep things simple to start. You have a lot going on just making sure the deployment is a success. And in fact, with a few simple metrics you can start measuring the success of the deployment.

Begin with **coverage metrics** that show the reach of your IAM program. Later on, you'll be able to assume that you're playing with a full deck and all your users, accounts, in-scope target systems, etc. are covered by your IAM system. Until you can make that 100%-coverage assumption though, it's useful to measure those percentages.

Even after you get to 100% coverage in your various dimensions, reporting on the pure counts of connected systems, onboarded users, etc. will continue to be useful to illustrate growth. These counts will also start to become inputs into more targeted metrics (average count per time, average count per user...). Starting with these coverage metrics is both immediately useful and lays good groundwork for the future.

In addition to illustrating deployment success, coverage metrics can also be tied to risk reduction outcomes with minimal additional work. Most organizations already have key risk indicators (KRIs) in place for their technology and security programs (if not, here's the part where it will take some work to define them). With a little documentation and communication, IAM coverage metrics can easily be tied to existing KRIs. 

Note also that KRIs are usually relatively static and thus easier to tie to coverage metrics, as compared to KPIs which frequently deal with the performance of some system or process over time. Stay tuned for more on KPIs next time.


#### How To Execute

Each IAM implementation will have slightly different user types, accounts, and targets in scope, but here's an example list to get you started.

* **Account and Repository Coverage** - these metrics show IAM deployment success when linked to a percentage of completion of project scope, and show risk reduction when linked to KRIs around Data Management Risk or Technology Vendor/Third-Party Risk if possible. If defined, any KRIs around IT Program Execution Risk are also easily supported by coverage metrics like these.
  - _Total number of connected systems/targets/repositories._ Seems simple, but if someone stops you in the hallway and asks how the project is going, rattling off this stat will illustrate a lot to someone isn't plugged in every day!
  - _Total account coverage_ - as number of accounts under centralized management grows, risk of (misuse|data loss|credential compromise) decreases!
  - _Account coverage by repository._ Potentially advantageous to categorize account repositories by Sensitivity (e.g., regulatory significance, risk, supply chain) or by Type (Applications versus infrastructure)
  - _Number of uncorrelated accounts._ Is this number growing or shrinking and why? It probably grows as you onboard more applications, which can illustrate the fact that there was a lot of distributed risk in your IT environment that has now been centralized. Hopefully this number shrinks to reflect your team's work on determining account ownership, closing dormant accounts, and overall reducing attack surface!
* **Authentication Coverage** - easy to tie to risk reduction when comparing the security provided by different authentication methods. Multi factor is more secure than single factor...what's your volume of each? Less tangibly, you might be able to measure user experience advantages by authentication method. SSO is a better experience than typing a password...how often does each occur? If defined, look for KRIs around IT Resiliency and Continuity Risk to tie to.
  - _SSO passthrough volume_
  - _Failed authentication attempts_
  - _Mobile and multifactor authentication_ could be factored in or broken out separately. It could potentially be advatageous to categorize your metrics by authentication endpoint.
* **Privileged Access Management Coverage** - security professionals understand the importance of privileged credentials in any cyber threat model, and should look for KRIs in Cyber Security and Incident Response Risk domains. Other than total account coverage, PAM coverage can be one of the headline metrics for demonstrating deployment success.
  - _Privileged Accounts onboarded or vaulted_ ideally broken out based on account types. Hopefully you have a PAM strategy that's already defined and prioritized your privileged access patterns. Shared accounts with high privileges (system, operational) usually present the highest risks.
  - _Proportion of Privileged Accounts with multi factor or next gen authentication._ OK great, they're vaulted, but if you have a default login with an 8 character password then there's a lot of room for improvement.
  - _Number of admin password changes per month_
  - _Number of emergency admin access events per month_
* **Counts of IAM Events** - if you have an IAM system in production, you'll be generating some type of event logs. Without needing to get into detail on *how* these events were generated or resolved, it can still be useful to track pure volumes.
  - _Number of approvals solicited by the IAM system_
  - _Number of resources provisioned_
  - _Number of reconciliation exceptions_
  - _Number of Separation of Duty violations_
  - _Number of certification decisions_


***Key Execution Detail:*** make sure you have at least *some* reporting requirements in your first IAM system release. Almost all packages come with some reports out-of-the-box, but you might be surprised what you *can’t get* without some customization. Make sure you've at least seen the list of OOTB reports, and hopefully even seen an example of each. A little foresight goes a long way towards making sure you have the right building blocks available from the get-go. 

However, don’t be afraid to combine reports outside of the IAM tool (e.g. in Excel) to get what you need. If you can get reports by identity, account, and target, you can get a long way with `=VLOOKUP`.


***Example:*** *If you have...*

+ *A report listing all Authoritative Identities, and*
+ *A report of all Accounts with their associated Identity*

*Then you can synthesize those to create...*

+ *A report listing all accounts from a specific target which are linked to a human identity, or*
+ *A report of identities with multiple accounts in a target, or*
+ *A report of accounts without an authoritative identity*
+ *etc.*
