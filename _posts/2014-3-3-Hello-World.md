---
layout: post
title: First post and "Reddit Asks"
published: false
---

Hello everyone, and welcome to my first post on **Notes from the Northern Cyber Department**, my blog on SOC management, leadership, and other topics.  If you're curious about me or the name, I recommend you check out the [About Page](https://dietz057.github.io/about/), where I discuss those topics.

For my first post, I'd like to introduce a type of article that I think will make up a lot of this blog, which I am going to call "Reddit Asks" - where I take a post from Reddit and provide my answer.  Of course I could just respond in the Reddit post itself, but I'd like to centralize my responses and keep track of them for my own reference and so people can easily digest my responses.  So without futher ado, here is my first crack at this:

## Reddit Asks: How do Red Teams Operate?
[Reddit Link](https://www.reddit.com/r/cybersecurity/comments/127w6w8/how_do_red_teams_operate/jeh93p3/?context=3)

On March 31, 2023, Original-Prompt4285 ("OP" from here on out) asked:

_Hello, as someone who is just starting out in red teaming, I have a question about ensuring the authenticity of red team exercises._

_My question is: how do red teams perform these exercises and ensure that the results are accurate? Do they typically attack from outside the network, or do they perform the exercise internally?_

_If red teams perform the exercise internally, how can they ensure that a real attacker would achieve the same results? After all, a real attacker wouldn't have the same level of access as the red team members._

Now, typically when I come across an interesting Reddit post, I'm typically not at my computer and therefore I don't reply or comment.  However, in this case, I was and I responded:

_I’d encourage you to also think broadly about what a red team can provide. Of course, a red team can provide pen testing services, which could be performed from an external source (which would make sense on some external-facing service) but also could be performed from an internal location (so the red team would be seeded on a workstation)._

_Beyond that though, red teams can provide a ton of value to an organization by testing its security controls - so they perform an attack and the SOC then observes whether the attack is blocked, detected, logged, or nothing happened (there’s a great tool called Vectr for this). In this case, your red team is serving as a mechanism to test the efficacy of your organization’s security controls._

_A red team could also be oriented to test your incident response process. So the red team could execute a full attack (spanning the kill chain) and intentionally trip a detect to test the incident response process of the SOC and related teams. This is often facilitated with some cooperation from internal users to generate the end-to-end attack._

_Basically, a red team can serve many purposes and what you want to accomplish will dictate the assumptions you should make. If pen testing, you likely want to act with the same restrictions an attacker has, since you’re trying to perform an objective assessment of risk from an attacker to the organization. If testing your incident response process, you can likely seed access a bit because you’re trying to test the response, and how the incident arises isn’t as important (since your SOC should be assuming that an attacker could get past certain controls)._

_I’ve rambled a bit, but I think you’re asking the right questions - so you’re going to be fine in your career. Good luck!_

I really don't plan on adding a lot to my answer, other than to emphasize how important it is to understand the underlying goals of your red team.  The rules of engagement for a red team really depends on what you're attempting to measure and the context of that measurement.  If a company is attempting to understand how much risk there is of an external threat actor accessing the environment, then the red team has to operate with the same restrictions as an external threat actor.  If the red team is attempting to test whether your antivirus detects mimikatz, then there really is no value in the red team restricting their access or capabilities to that of an external threat actor.  In fact, they shouldn't do that as it just adds cost to the assessment (in terms of time and money).  

To cap this off, I think it's worth making clear that understanding your goals is not just advice I would have for a red team - it's for all security professionals (and maybe people in general).  I know from experience that it's easy to get an idea and charge head first into execution without really understanding what you'd like to accomplish.  


