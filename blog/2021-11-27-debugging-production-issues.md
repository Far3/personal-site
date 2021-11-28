---
title: How to debug and troubleshoot production issues
path: /how-to-debug-and-troubleshoot-production-issues
date: 2021-11-27
summary: Step by steo how to debug and troubleshoot production issues
tags: ['production', 'debug', 'troubleshoot']
---

If you've been a software developer for any length of time,  you have had to deal with or be involved with a production support issue. This is doubly so if your application is client facing, ie. facing the general public and has high importance that it is working during peak times. This could be during busy market days or during a huge sale. Uptime is critical.

On-call is usually on a rotation basis and different companies have different policies. Let's say you get the call, tier 1 support will reach out, tell you a general description and ask that you get online. Before hastily jumping online ask these three questions to get your bearings.

-   "What is happening?"

-   "Where are we at?"

-   "What did we try?"

These questions will give you a general idea of what is going on and may jog your memory and spark a  question that they can look into. Typically support calls interrupt you when you're relaxing at home and not in prime work problem solving mode.

Ok, so you hop online brain foggy, coffee pot not filling quick enough and you're on a  bridge with a bunch of people, amazing!

Now what?!

## Replicate the Issue

Always replicate the issue by yourself. In web development, some tricks to reliably replicate issues are to try it in an  incognito browser as some extensions may mess with default behavior.

If the bug is intermittent and can't be reliably reproduced, this means that you need to keep digging and still get the steps required to reproduce the problem. If someone says "It's intermittent or it's non-replicable" that's BS. More research needs to be done to understand the root problem. A common example is if something 'seems' intermittent, it is usually a server issue and narrowing it down to a specific server or node will help.

## Mitigate Impact

The next item once it's been reliably replicated and you gain an understanding of what piece of the system is breaking, is to mitigate impact if possible. You are being called because the client/company is losing money either directly or through losing credibility because their site is broken and a lot of people are seeing it.

Every companies hosting strategy will be different, but most companies will have some form of backup or way to deploy the code to a different location. It could be multiple data centers, multiple instances or containers. In my experience there were multiple data centers and simply moving all traffic to the other data center mitigated the impact while uncovering the root cause.

## Search back in time

My favorite thing to do and a seemingly unknown tactic is to simply search back in time. Its true that each issue has the potential to be unique. Most of the time it's not. Search ticketing systems, intranet, teams/slack/messaging chat history and support base. I've had it on more than one occasion where I got lucky and this problem has occurred before. I pieced together the solution from multiple tickets and chat histories. Then I documented it myself so future developers and support engineers could learn and solve this issue I was facing that much faster.

## Narrow down search

Keep narrowing down your search and coming up with hypotheses on why XYZ is happening. If there are 2 data centers, each with 4 servers, then check each individual server and hit 101a, 101b, 101c. It's quite common that one of them will be in a bad state. Another option is to narrow it down by service, since web development is a lot of interconnecting technologies, test out each service and see where the point of failure is.

### Some Common ones

-   Do you  get a response from the API? 
Is it giving an error message that could indicate the authentication is an issue such as an expired certificate or password.

-   Do you get data back, but is the data wrong? 

-   Maybe reach out to the database team and dig into how that data is ingested.

-   Front end page or module not rendering? 

-   Possibly a data type change and error handling was not implemented.

Sit and think. No really, just sit and think through the problem occurring at hand. This can be tough to do, because support or a client  is often asking for your update quite frequently. Sit and think and even write it out on a pad or draw what is happening and some ideas may come to you. You could even talk out loud like rubber duck debugging.

## Be overly communicating about what you find.

As mentioned earlier, you will be bugged quite a bit for updates and what progress has been made. "Still investigating" is a perfectly fine answer. A better answer would be to over communicate what your findings are. I'm doing x, I suspect it's y, I am trying to do Z. Oftentimes others can chime in and possibly help you in your debug efforts. Another benefit is if someone has already ruled that problem out, they will let you know before you invest any more time into it.

## If still stuck, reach out to other experts

Everyone eventually needs to call for help at one point or another. It could be because they don't have permissions to view or access something. It could be they don't have the domain knowledge on that particular part of the system. Or you are just stumped with your back against the wall. This happens and is normal. It's important when calling another resource after hours to have the three questions I posted ready to go. It ensures no time is wasted and you made a solid effort instead of "I dunno, just call the tech lead".

-   "What is happening?"

-   "Where are we at?"

-   "What did we try?"

## Document your solution

So you did it, you were able to replicate the issue, mitigate the impact and narrow down your search. You pieced together past tickets and messages and had a few hypotheses. Some were wrong, but a few got you in the right direction. You posted updates to the production support chat room and others chimed in and helped jog your memory of the application. You tested a final hypothesis before calling in backup and it turned out to be 100% correct. Congrats, this is a great feeling. A fix was implemented, ie server restart, config update needed, cache busted..etc and the client is happy, support is happy..you're done right?

No

This might be the 2nd most important step next to replicating the problem. It is documenting the solution. Document the steps that you took, post comments step by step in the ticketing system or better yet your production support document. I've seen a "common issues" section and this will help the future developer that gets called late at night or super early in the morning. That next dev could be a close colleague or even better tier 1 could handle it on their own. They will be thankful you did and reduce the [bus factor](https://en.wikipedia.org/wiki/Bus_factor).

## TLDR

-   Replicate the Issue

-   Mitigate Impact

-   Search back in time

-   Narrow down search

-   Sit and think.

-   Be overly communicating about what you find.

-   If still stuck, reach out to other experts

-   Document your solution

