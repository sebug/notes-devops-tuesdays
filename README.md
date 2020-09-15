# Notes Devops Tuesdays

## September 1 - Navigating the Cloud Native Seas
Bridget Kromhout, Delyan Raychev

People are still very interested in service meshes


### Most common service mesh capabilities
- Traffic Policy (for example: identity, transport encryption)
- Traffic Telemetry
- Traffic Management

### How is it implemented?
Custom Resource Definitions for Kubernetes

Example: https://github.com/servicemeshinterface/smi-metrics

## September 8 - Fireside Chat
John Willis

Didn't know you could get a PhD in transition design :-)

Today, CI/CD is table stakes (difference between 2010 and 2020). "For some people it's novel".

But we're only halfway done.

3% club vs 97% club - what do you want to belong to?

Literature is great and you just have to be really intelligent.

Where in the hierarchy should a DevOps transformation start? Ideal scenario is top down. But not everybody has the luxury of having a CIO that wants that.

If you love your company / want to stay there. Do the grind.

Courtney Kissler - Nike https://www.youtube.com/watch?v=J-vT4BjEYL0

Top 3 problems for struggling companies:
 - Consistency
 - Trust
 - Toil

Hat tip to the Team Topologies book.

Seven Deadly Diseases of Devops. https://electric-cloud.com/blog/qa-with-john-willis-the-7-deadly-diseases-of-devops/

Intent-Based Leadership.

### How to get started?
Before: Value stream mapping / Value chain mapping. But for him, he doesn't like
to bring them in too early.

"How do I do X?"

"You go to Bob"

"Bob, I prefer not to come to you next time, how do I do this myself next time?"

Seek and destroy those instances!

Horizontalize Bob (Brent).

Empathy! Watch the David Foster Wallace commencement speech. https://www.youtube.com/watch?v=8CrOL-ydFMI

"I didn't realize, I just thought you guys weren't that efficient".

## September 15 - Security Learns To Sprint
By Tanya Janca @SheHacksPurple

Alice And Bob Learn Application Security

Do your job as securely as you know how to do.

If Software Developers are sprinting, Security Folks are sprinting too - so you'll have to organize accordingly.

Poor AppSec causes between 29 and 40% of breaches. *Insecure Software is a Disaster*.

### Security is Outnumbered
Dev / Ops / Sec : 100 / 10 / 1

### DevSecOps

- Emphasize the efficiency of the *entire* system
- Fast Feedback
- Continuous Learning

CIA Triangle: Confidentiality, Integrity, Availability

Security doesn't win if the business doesn't also win.

### What does that mean for your pipeline?
- Severe Security Bugs break the build

### What does it mean for Security
- Can't be the bottleneck
- Only break if it's actually important
- Break security activites in smaller pieces
- Just make a pipeline that goes nowhere, doesn't stop your regular pipeline.
- Write libraries
- Buy licences for the security tools you expect the team to use!
- Provide feedback as early as possible

### What do you need to do as a Dev?
- Provide Feedback on the tools
- Participate in security activities

### Question: Would you run those security tools in prod?
Sometimes. Good example is the Canadian Army - they have a team constantly cyber attacking their colleges, just to stay vigilant.

Problems: Load, the tools themselves may not be ultra secure. Maybe after hours.


