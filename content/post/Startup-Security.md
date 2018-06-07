---
date: 2018-04-20 14:05:01 -0500
title: Startup Security
authors: []
categories:
- 
tags:
- 
draft: true

---
part of intro - tptacek comment at top of this thread: [https://news.ycombinator.com/item?id=17014818](https://news.ycombinator.com/item?id=17014818 "https://news.ycombinator.com/item?id=17014818")

The answer isn't quite "don't bother" but it's definitely not "install these tools and get started".

Most of the things you can easily set up to watch for security events are looking for problems you simply shouldn't have.

For instance: you can set up fail2ban, sure. But what's it doing for you? If you have password SSH authentication enabled anywhere, you're already playing to lose, and logging and reactive blocking isn't really going to help you. Don't scan your logs for this problem; scan your _configurations_ and make sure the brute-force attack simply can't work.

The same goes for most of the stuff shrink-wrap tools look for in web logs. OSSEC isn't bad, but the things you're going to light up on with OSSEC out of the box all mean something went so wrong that you got owned up.

Same with URL regexes. You can set up log detection for people hitting your admin interfaces. But then you have to ask: why is your admin interface available on routable IPs to begin with?

What you want is an effectively endless sink for developer logs (Splunk is fine but expensive, ELK is fine but complicated to manage), and you want to add structured instrumenting logs to your applications in all the security-sensitive places, like authorization checks (which should rarely fail), and especially a very solid, very long-term audit trail of admin-like actions, so you have some prayer of tracking insider misuse. You could instrument your SQL queries and catch any query failures --- which should also be rare. That kind of stuff. I don't think there's a good shrink-wrap package that does that.

But really: focus on removing attack surface, rather than continuously monitoring it.

  

Startup Security
https://www.sqreen.io/checklists/saas-cto-security-checklist