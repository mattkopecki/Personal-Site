---
date: "2018-01-01T15:00:00-05:00"
title: "IGA/PAM Integration Pitfalls"
authors: []
categories:
 - 
tags:
 - 
draft: true
---

*Critical decision points in PAM integrations*

1.Reduce overall complexity of layered authorizations, or reduce risk by enforcing least-privilege in a complex layered scheme?

2.Introduce a new account type “Privileged Shared Accounts”, or vault existing 2ndary Admin Accounts owned by administrators?

3.Model authorizations in centralized enterprise repository (AD or other directory), or locally within the PAM tool?



Privileged shared accounts - new account type introduced when doing PIM/PAM

- Do admins keep their own secondary accounts and we vault those, or should there be new service accounts that people share?

- There's no problem with privileged shared accounts, but the implications that come with it

- It's a New account type - what kind of controls over secondary admin accts? Monitoring, group policies, etc. needed? Requires new lifecycle processes, new model of ownership

- Easier to reduce risk and not break existing processes is to use existing secondary accounts



Modeling authorizations in centralized enterprise repository (AD or other directory) versus locally within PAM tool

- how do you model the authorizations in CyberArk? PAM module shows groups, containers you're provisioning to, but also lets you see what servers are in the group and what policies are applied. Without the module, you only see that someone is in and AD group and that's it. PAM Module does support AD groups as well for the authorization, but then need some way to support discovery of which AD groups are the CyberArk ones, e.g. through naming. and need to create a lot more resources and map them together before anything works, need to create AD group, CyberArk entitlement, IIQ entitlement, map them all together. If you just have the PAM module with no AD in the middle, you could just aggregate and be done.

- In CyberArk they need to configure a complex authorization model that will surface to IIQ what is available to be managed



Overall complexity of authorizations. Layers - any could affect (choke) the access such that it's limited

- 6 layers
  - Whether they have access to a vault
  - What the PAM Policy is on their group or vault
  - Access to an account within PAM
  - Whatever authorizations or groups that account has assigned to in the target system
  - Servers or assets listed in the vault (used to scope what you can jump to)
  - Endpoint policies on the server (e.g. powerbroker, avecto, CA endpoint, etc. other endpoint technologies)

- If you own just one of these layers, sure you'd design it and manage it beautifully. But when you have to manage all them together, how do you troubleshoot access issues? Do you only manage access at a few of these layers? At all of them?

  - Think of managing file and NTFS share permissions - you usually leave share permissions open, and then just manage permissions at the folder level so that it's easier to manage. Leave one level open, and then robustly control at the other level. That's just two levels…

  - Now, think of Servers in the vault, versus what account you have - could control in AD what account can do and limit what servers they can access, but leave it wide open at the CyberArk level. But that makes it look from CyberArk like they have access to everything, but realistically they don’t. they can try to remote to any server in this scenario, but they’ll only succeed at some of them. So, decide whether to manage this access at one level, the other, or both, but need to think about implications in terms of visibility versus ability to manage
