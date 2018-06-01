---
date: "2018-05-31T18:05:01-05:00"
title: "IAM Metrics Part 3 - Measuring New Ways of Doing Business"
authors: []
categories:
  - IAM
  - Enterprise
tags:
  - metrics
cover: /images/metrics-3.jpg
draft: false
---
***It can be difficult to know what to measure at which stage of your IAM implementation.***

[In Part 1 we talked about some IAM metrics you can use to measure Deployment Success and Risk Reduction](http://mattkopecki.com/post/iam-metrics/) and [in Part 2 we talked about IAM metrics you can use to measure performance of your existing business processes.](http://mattkopecki.com/post/iam-metrics-part-2/)

Without doubt, reducing risk and streamlining existing business operations are great benefits of IAM.If you can say _we did more of these items in less time_, there's nothing bad about that!

But if you can say _we don't do those items anymore because we can just do this instead_, that's better. Here are some ways you can measure your IAM program to demonstrate how it's enabling new ways of doing business.

#### How To Execute

**"Shifting Left" With IAM Process Improvements**

Shifting left means moving reducing administrative workload by educating or enabling users to easily execute an action that previously was centrally managed at a large cost. 

(Why is this "shifting left"? Picture a left-to-right flowchart of the tasks in that administrative process. After your implementation, the responsibility moves back to the left and shortens or simplifies the process.)

For example, any time you can prevent the help desk from answering the same questions over and over again or completing simple transactions that customers could handle by themselves, that is shifting left.

Your IAM tool does these things, so you should measure and report on them!
  - Demonstrate the effectiveness of a password management deployment by measuring how many password resets have been redirected from the service desk into an automated tool
  - Measure reduction in total number of events through SSO rollout and password synchronization improvements
  - Measure the number of approvals or certification decisions _not needed_ because of your entitlement classification scheme that only submits the highest risk items for multiple reviews
  - Measure the shift from individual access requests to access requests bundled into roles. Roles pull upstream the work of finding and submitting all your individual entitlement requests.
  - Measure the impact of form or process validation rules that reduce unneeded work


**"Shifting Up" With IAM Automation**

If shifting left meant moving upstream in the same general process, shifting up means moving from one process to a newer one.

In IAM's world, the biggest class of these types of process shifts are whenever you can move from request-based actions to policy-driven actions.
  - Attribute-based access assignments made, versus request-based role or entitlement requests provisioned. Even if you don't have an ABAC strategy and haven't written a lot of XACML, you probably still have "birthright" access that you assign throughout your user lifecycle so be sure to include that.
  - Policy enforcement decisions versus individual review of events. These save time, increase consistency, and remove the least attentive and most vulnerable link in the chain (the human).
  - Rule-based data/metadata enhancement replacing manual effort. Are you using rules to correlate accounts to identities where you hadn't before? Are you using rules to build your access catalog or create identity attributes when you reconcile/aggregate data? These things used to be done through spreadsheet wizardry, if anyone was doing them at all.

After you have collected your metrics from Part 1 and Part 2, stacking these types of business transformation metric on top can really hammer home how important your IAM deployment has been to your enterprise.
