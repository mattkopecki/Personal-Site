---
date: "2222-04-20T14:05:01-05:00"
title: "Perspectives"
authors: []
categories:
  - 
tags:
  - 
draft: true
---

somthing like this, maybe with IAM perspectives - Cryptographic Right Answers
http://latacora.singles/2018/04/03/cryptographic-right-answers.html

**Top Perspectives**

- Top perspectives: most interesting topics in Infosec
  - azure sphere - 565 psw, 27 asw
  - that crypto puzzle research

**RBAC vs. ABAC**

- ABAC is great for authorization. But it is terrible for management, accountability, analytics, identity governance and other high-level methods of information security.

**Big Data**

- In general, a Data Lake is a good name. What do lakes do in real life? The just kind of sit there. Sometimes like 0.01% of it froths a little bit. If you don't have a data-driven challenge that needs to be solved beforehand, adding your data to a big lake won’t really move the needle.
- The surrounding ecosystem is really starting to mature, and distros like CDH actually make a lot of sense.

**Security Analytics**

- The biggest problem right now is that it doesn't actually do anything, it just lights up dashboards and makes work for analysts. Could be an interesting foundation for RAdAC though…
- Risk based certifications are something that excites executives, and might actually work too, but the ranking algorithms are all made up (what are the best practices for configuring these? Just pick some presets…) and no one is really using this in practice

**Agile**

- Both Agile and waterfall methods attempt to give you a pattern by which you can predict when software will be delivered. The single biggest benefit from Agile is controlling risk by getting the customer in front of the software sooner, so it can be iterated based on feedback. The primary risk being controlled is building the wrong thing. If the primary risk to your project isn't getting the user experience right, then Agile isn't the right framework.

**Identity Theft**

Suppose Alice is a "victim of identity theft". BigBank gives $10k to Fraudster as a loan, thinking that Alice is the actual recipient. Experian, Transunion and Equifax report this loan as a debt which Alice owes to BigBank.

Who is the real victim? The credit reporting agencies want to convince people that the consumer is the victim, and so Alice bears the burden and risk of clearing her name. But it is the credit reporting agencies inflicting this upon Alice. BigBank is the victim who lost money, and BigBank bears the responsibility for making the mistake of giving out a loan in Alice's name. The Fraudster committed a crime against BigBank, not against Alice. It is Experian, Transunion and Equifax, by holding this fraudulent loan against Alice, who are victimizing Alice.

The idea that Alice was victimized by Fraudster is a concept being perpetuated by the credit reporting agencies as a way to absolve themselves of responsibility, and place the burden upon the consumer, and to avoid realistic identity-verifiction which might slow or complicate the practice of issuing large amounts of debt to the general public.

**Data Science**

Some say "You Can’t Do Data Science in a GUI", but people make the same argument against Wix and Squarespace - "you can't make a website in a GUI".

Yes, you can - but you'll be pretty limited. If you're a brick and mortar or service focused business, a website builder is great. If you rely deeply on a customized web experience, you need to do something custom.

Same with data science. You can get pretty far with some simple data analysis tool. If you need to go farther, then you need to build custom solutions.

**Privileged Account Management**

- Very important, but what you really need is a full secrets management program that starts with all software dev, plus controls that enforce that there are no secrets in any code
- Two most important parts are robust secrets management ("vaulting" with proper procedures like key rotation etc.) and then making sure that the vaulted entitlements are onboarded to an IAG tool and associated with users. Monitoring, analytics, etc. are cute but they're really peripheral 

**Certification**

- No one wants to do it, but at the end of the day this is what it's really all about. Thanks SOX

**Cloud Identity Management & IDaaS**

- If you're using spreadsheets now, which a ton of people are, then this is a great option.
- If most or all of your apps are third party web apps that you access over the internet already, then this is may be the way to go too. It's easier to just put everything in the cloud in that case

**Risk Adaptive Based Access Control (RAdAC)**

- Requires a pretty fundamental perspective/culture shift to be ok with the idea that the system may adapt its decision thresholds such that operational need can trump security risk when appropriate…meaning that someone who otherwise wouldn't get access may actually get it
    - e.g. someone without a security clearance could get access to clearance-required information if they're computed to be trustworthy enough
- RAdAC whitepapers (PDFs) 

**Access Management / SSO**

- Death to passwords is very important

**Identity Federation / Identity Data Store & Virtual Directory**

- Managing disparate populations and their entitlements across different data silos continues to be one of the hardest challenges in identity management. Dealing with consolidations, mergers and acquisitions, enabling cloud applications, integrating with partners, or extending access to mobile devices is still very difficult even if you’ve made heavy investments in WAM packages, federation tools, and policy servers.
    - Luckily, the technology is all there to solve this. 
    - Unfortunately, the process and the IAM Service sides of this are the hard parts, followed shortly by the actual authorization decision making (but granting authorizations if you already know who should get what access is solved though)

**Role Life Cycle Management**

- There really is no best practice for this other than what you get out of the box from your vendor, and none of it is robust. State of the art for this is still spreadsheets and SharePoint sites unless you happen to have Saviynt maybe

**Privacy**

- Privacy will become the main business objective, and the security function will serve that business objective
- "Arguing that you don't care about the right to privacy because you have nothing to hide is no different than saying you don't care about free speech because you have nothing to say," -Snowden
- To me, the main issue is accountability. A citizen's data can be collected, badly secured, stolen, and used by criminals without the user ever being aware of step 1. Just like a citizen can get ill from swimming in a river without ever being aware of the factories upstream. The solution is not to force citizens to constantly be on the lookout. It's to severely punish polluters and leakers. When a CTO says "let's collect geolocations", the CEO should have legal and business reasons to say "no way, it's not worth the financial risk of losing them; it could destroy our company."

**DevOps Security**

- http://www.devsecops.org/blog/2016/5/20/-security
- https://www.sqreen.io/checklists/devops-security-checklist

**Identity Intelligence & Analytics**

**Data Access Governance (unstructured data)**

**Password Policies**

**GDPR**
- The problem is that when we outsource thinking to machines, we are really outsourcing thinking to the organizations that run the machines

