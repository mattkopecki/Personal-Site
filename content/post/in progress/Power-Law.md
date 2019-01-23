---
date: "2018-08-15T14:05:01-05:00"
title: "Power Laws in Cybersecurity"
authors: []
categories:
  - Cybersecurity
  - Enterprise
tags:
  - Leadership
draft: true
---

**Power Laws**

- 1. reminder, even though a lot of what happens around us from a day to day perspective doesn't operate based on power laws, in cybersecurity we operate in a universe that's governed by them.
  2. knowing that we're in a power law world, how do you defend?
- Ask yourself how do we know that “average/mean cost per record or number of vulnerabilities or whatever” is a good summary statistic
- Measure things in quintiles and think about each quintile
- Rethink how to communicate and visualize uncertainty - good examples in paper “when-ish is my bus”
- Risk matrix with low medium high actually adds risk (there is research for this) so it’s dangerous
- Risk management matrix avoidance acceptance mitigation transfer



http://blakemasters.com/post/21869934240/peter-thiels-cs183-startup-class-7-notes-essay

Despite being rooted in middle school math, exponential thinking is hard. We live in a world where we normally don’t experience anything exponentially. Our general life experience is pretty linear. We vastly underestimate exponential things.  







http://scholarcommons.usf.edu/cgi/viewcontent.cgi?article=1439&context=jss









fred wilson - how do we make X conform to a power law?

me - consulting - what activities can we do in consulting to make consulting conform to a power law?





**Episode 29** - Data Driven Security Podcast

what do you think is the average of [events]? that's not really the right question

power laws are a type of mathematical distribution that turn out to be important for decision makers in cybersecurity.

power law is a mathematical relationship between how often events of different sizes may occur. one distribution we can use as analogy is the normal distribution (or the bell curve) basically, this means that the vast majority of observations will cluster around the mean, and then the larger and smaller observations fall of pretty quickly in to the tails. so things like the height of humans turns out to be normally distributed, rainfall events, etc. 

it's well understood, but it describes a specific type of mathematical relation ship. a power law is a different one. it's x to some number or parameter.. x squared, x to any number. a relationship between two variables of interest

think about height again. most people are, say 6 foot high with some that are a little taller or some a little shorter. 

contrast this with income. income turns out to be something in the US that's distributed like a power law. there are a huge number of people that make between 50k-100k. then there are fewer people that make 100-500k. and then you can go up orders of magnitude. there are many fewer people that make tens or hundreds of millions of dollars per year...but there are those people that in fact exist. 

in a power law relationship, what you often find is that the variable of interest is often distributed across orders of magnitude.

think about the normal distribution of height again. if height were not normally distributed, but it was distributed like a power law, what you'd see is that most people would still be around 6 feet tall, but then there would be one person in your state who would be 10 feet tall, and there would be one person in the world who would be over 100 feet tall. that's clearly not the world we're living in.

so either way, it's rare to have these outliers. but in a heavy tail distribution like a power law distribution, these outlier observations/events are actually more common and impactful than you'd expect.

in cyber security, these heavy tail distributions actually come up a lot. power laws occur in lots of other things, so it shouldn't be surprising. but for a lot of people, power laws are something that people aren't familiar enough with for us to expect them.

it's not that interesting to just point out that something like cyber security has events that are distributed like a power law. blog post: so you found a power law, so what?

what's important is thinking about what impacts will it have on my work and on the decisions i make, knowing that we're living in a system/world that conforms to (is governed by?) a power law.

why does this actually matter in your daily life as a security professional?

- power laws typically have these incidents that occur across orders of magnitude => think about the monetary cost of hacking incidents to your org. lots that cost you nothing, like port scans or low level things blocked by email filters. smaller number of more impactful incidents. every once in a while someone defaces your website, a laptop goes missing, someone sends you a phishing email. even more rarely, there will be a hugely impactful incident...something that may take 1000 times more time/money/effort to resolve. the Chinese get into your system, you release PII due to a misconfiguration, etc. 
- when youre trying to make decisions as a security professional, use the right tools. if something conforms to a normal distribution, we have statistical tools we can use like a summary statistic like a mean, std deviation, variance. these work to describe things that are like a bell curve. for a power law, it turns out that the mean is a really bad representation of that distribution. so things like average cost to an organization due to a data breach cant be represented as a mean or median. cost per record compromised, etc.
- need to contoinue to push the boundaries on what is the best metric to make these decfisions with
- risk assessment tools - Value At Risk metric, lots of people are fans of this metric. it's an acceptable risk metric for normally distributed events. for power laws, it's really bad.

What to do next?

- get an intuition for what a power law is and what they look like
- got data? there are some things you can do get a feel for whether your data follows a heavy tail distibution. look at a histogram if you can of your data. you're looking for something that looks kind of like a normal distribution but then has a heavy tail. look at your logs, etc. For a normal distribution, those large incidents are so rare they basically never happen. but if you see the large incidents, it's a clue you might be looking at a heavy tail distribution. e.g. ticketing system, most tickets are closed within 1 day to 2 weeks, but there are a few tickets that take a year or 2 to close.



the power law of information security: nothing is linear (2014 talk)

exploitation counts for particular vulnerabilities. exploits for certain CVEs. CVSS score distributions. remediation rates of vulns. the types of assets or software. all don't have an average with a variance. distribution (frequency) of an attack type is power law distributed. impact of breaches/number of records lost has no real mean. the tail is very fat. it's entirely reasonable to expect the next breach to be of absolutely any magnitude.

what would be the implication if these distributions were normal? what could we do with that knowledge?

counter-terrorism and the severity of war (attacker defender interaction, something with another opponent). 

maybe come up with a lower bound, and a higher bound, that make sense

the next event we observe could be an order of magnitude worse than the previous one. given the way tech works, that kind of makes sense. 

underlying process that's generating cybersecurity incidents - about the same that generate insurgent terrorist activity. probably just related to measuring human action.

so what?

- you need to assume that swans are coming - need to build some sort of resistance to some of these scenarios that are way outside the bands of what you normally expect. making sure the interdependencies of systems are not so high that all fail at once. making sure you have a manual fallback.
- risk needs to be modeled differently across cyber security. a lot of our risk modelling is based on averages and standard deviations based on previously observed data. think not interms of averages, think in terms of quantiles. the way we do with hundred year floods, 500 year floods, and planning for those. good news, this has been dealt with in other industries (flood insurance). need to model these things as an evolving process that could get worse and worse.
- mistake people make: look at average number of vulnerabilities per asset, and then instrument some metric or dashboard that shows that that number is declining. that might be great in the normal distribution regime. but in the power law regime, when the tail is really fat, the difference between the 99th and 99.9th percentile is astronomical, and that's where a lot of the risk resides. strategies need to be tailored to reducing that risk. reducing things that may be incredibly risky, but go unnoticed. the simple takeaway is: evaluate not the average counts, but think about strategies that reduce the exposure across the enterprise. pluck out the top and look at the riskiest vulnerabilities on 100 diff assets and remediate those. then, your remediation actions themselves become fat tailed because you're addressing the things that are towards the right side of the distribution.

a lot of the tooling we have tends to lead us down this path towards averages etc. 

practitioners need to begin to look at things in this distribution sense.

model everything out in quantiles. this is an available tool in excel. when you look at that, you'll see that sometimes what you previously thought was a huge effort had no impact on your upper quantiles.

log normal or power law? how to model? who cares. if we agree the tail is really fat, there isn't really a tangible takeaway for practitioners in terms of what you need to do.