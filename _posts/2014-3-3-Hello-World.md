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

_Beyond that though, red teams can provide a ton of value to an organization by testing its security controls - so they perform an attack and the SOC then observes whether the attack is blocked, detected, logged, or nothing happens (there’s a great tool called vectr for this). In this case, your red team is serving as a mechanism to test the efficacy of your organization’s security controls._

_A red team could also be oriented to test your incident response process. So the red team could execute a full attack (spanning the kill chain) and intentionally trip a detect to test the incident response process of the soc and related teams. This is often facilitated with some cooperation from internal users to generate the end-to-end attack._

_Basically, a red team can serve many purposes and what you want to accomplish will dictate the assumptions you should make. If pen testing, you likely want to act with the same restrictions an attacker has, since you’re trying to perform an objective assessment of risk from an attacker to the organization. If testing your incident response process, you can likely seed access a bit because you’re trying to test the response, and how the incident arises isn’t as important (since your SOC should be assuming that an attacker could get past certain controls)._

_I’ve rambled a bit, but I think you’re asking the right questions - so you’re going to be fine in your career. Good luck!_

I wanted to expand a bit on my answer here, because OP had a really great question that reminded me of an important principle - and that's to let your goals guide your execution plan.  I think many professionals (and I'm about to sound like a project manager - which I occasionally am), neglect to think about the goals of their project before actually executing them.  And for the purposes of this, interpret the term "project" broadly to mean anything you do that's valuable. The reason why you need to focus on your goals is because that is going to impact your requirements (more project manager talk!) - and you can see me getting at that in my original response.

So, what I'd like to do with the rest of this post is describe some of the goals a red team can seek to fulfill and then discuss the requirements of each as I see them.  Take this with a grain of salt, as I am not and never have been on a red team.  That said, I am the consumer of many red team findings and the person they seek to help, so I have a decent amount of experience thinking about how to successfully utilize a red team.  Here we go:

Red Team as Vulnerability/Misconfiguration Detectors (Pen Testing)
Goal: Identify vulnerabilites or misconfigurations in an organization's environment.

So, I don't want to conflate "red teaming" with "pen testing" but I think many job postings treat these terms interchangably, so I want to discuss it here.  From my perspective, a core function performed by a red team is penetration testing, which is when the red team is attempting to locate vulnerabilities or misconfigurations in their organization's environment.

A fair question is: why do we need the red team to perform this type of service when there are vulnerability scanners (Qualys, Nessus, ect.) and configuration compliance systems (SCCM, AWS Config, etc.)?  From what I've observed, there are two reasons. First, these tools are largely limited to known pieces of software.  So if your organization has built a custom app, a configuration compliance tool isn't going to know if something is misconfigured because it has no knowledge of what the proper configuration should be, where a red team could use some human intuition to recognize that a business rule isn't being properly enforced.  Second and closely related, a red team may be able to conduct more complex and/or novel exploits than a vulnerability scanner would be able to accomplish.  Generally, a scanner is only looking for vulnerabilities or misconfigurations that are already known.  A red team may find something new the same way a potential attacker would.




