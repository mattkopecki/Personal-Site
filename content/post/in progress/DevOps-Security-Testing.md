---
date: "2018-01-01T15:00:00-05:00"
title: "Title"
authors: []
categories:
  - 
tags:
  - 
draft: true
---

Perspective: security testing (see asw 24)

- areas where you can/will apply some security solution to your development process
- \0. Threat modeling —> decide what breaks a build —> training
  - as an organization, need to (get to!) decide what types of vulnerabilities will break a build versus which wont. by the way, this is what it means to have a "culture of security" in the most practical sense. if you say that these things are important, and then enforce it, then you're headed there. 
    - tie to Masha's security culture stuff. 
    - tie to "how did we get to a point where security is different from quality"
  - don't let the tool define your process, start by defining your process and then youll actually follow it. define an exception process, but think really hard about this part. once you start letting everything through, or start ignoring things, you run in to broken windows theory and all of a sudden you'll have developers who are numb to alerts, a slow development process with a ton of red tape AND a bunch of bugs in production.
- do these things as far left as possible
  - \1. Static source code analysis (pre push to version control, or post push) or static binary analysis (post push to vcs) - choose one, but the closer you can get to the developer e.g in the IDE is better because it’s the fastest feedback. However goal should be to minimize false positives even at the expense of finding everything (which is an argument for doing on the binary actually, you’ll tend to get fewer false positives there)
    - compiled or interpreted software? could help sway this solution, becuase some of these solutions may not apply. but this is the wrong way to think about it, trying to match the technology with your technology. instead, try to match the process with your process. so do *something* before vcs push, something after it. match to stages of development.
    - recommendation: do both but optimize them for different things
    - so, IDE feedback is best because it's fastest, but you don't want to break the build on many of these things because of the potential for false positives. dynamic scanning and binary analysis should be able to break the build. it takes longer to run, but runs in parralell to unit tests  or integration tests, but when you find sometyhing you can say that it's very liukely a real problem so you have to break the build there
  - \2. Analyze repo for vulns (and/or licensing issues) in dependencies and open source software. if you can do this BEFORE the repo that's even better because at that point it won't be a shared dependency yet, and once it is it will be much harder to unwind. but depends on your tooling whether you have this capability.
- \3. Dynamic analysis and testing
  - static binary analysis (post push to vcs) AND dynamic application scanning solution at unit test time - these things need to be fixed before getting to integration testing
- \4. Container/infrastructure/orchestration/operational security
- \5. Waf, rasp, iaas, web protection etc. - monitoring your application for attacks and unexpected usage, and monitoring in real time fr vulnerabilities and unexpected behavior
  -  \- asw 29 at 50 mins tcell vs signal sciences
- \6. feedback 
- ASW 24 notes