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

## September 22 - Fast And Simple: Observing Code and Infra Deployments at Honeycomb
Shelby Spees @shelbyspees

They are a similar size - a dozen people.

As long as people are working, changes roll out (from 10 to 14 times a day).

### What does it look like to ship to prod?
- Observability-driven development: How will it look like when the feature is deployed in prod?
- Tests (functional and UI)
- Feature flags ("no-op deploys" - put the changes in prod not enabled for anybody).
- Builds shorter than 10 minutes
- Automated review
- Human PR review (review everything, then you don't have to judge whether it's worth it)
- Observe behavior in prod

### Dogfooding
Observe Honeycomb with Honeycomb.

Kibble observes dogfood observes production (those are not staging environments but real ones).

### How did they start improving?
- with lead time: hours to deploy a change
- change fail rate goes down. If you mess up, deactivate the feature and fix forward
- feature flags are meant to be temporary to avoid exploding combinations (a dozen feature flags at the same time max) - this works because there's not a lot in-flight (methinks: so maybe not start with that when your lead time is still long)


Question: When do you look? When the feature is used: may be today, may be in a couple of weeks - so that's where observability comes in, you really get a feel when the feature gets used.

Who looks? Mostly devs.


### On the infrastructure side
Keep it simple (no conference-driven decisions). Automate the painful parts.

They use raw VMs - start where you're at. But: Infra hygiene!

Hosted Terraform - release from the website.

Feature flags for infra as well (mainly who gets which instances I guess?)

Use SLOs to determine whether the errors are not too bad - allowed unavailability.

### Sample SLOs
Ingest: 4 nines

Dashboard: 3 nines

Queries: 99% in under 10 seconds

So what did that mean for the ten minute outage that was the example? They burned through the whole error budget quite quickly. Then it's important to communicate.

What happened: They deployed empty binaries.

What they did: Stop the presses, improve stability before going back to features.

Slides etc: https://www.honeycomb.io/shelby

## September 29: Building and operating applications in the cloud
Seth Vargo (Learning Chef, SRE...)

### SRE
Care deeply about

- Scale
- Reducing toil
- Automating as much as possible

### We probably don't need an SRE person
Whenever the reliability of the system is someone's full time job. That person
should report to an engineering manager.

### Google SLOs can be accessed by everyone in the company

### SLO is an unavailability target
The point is not to beat the SLO, meet it. If you're exceeding the SLO, you're
delivering more availability than you promised.

Intentionally take down the service to meet SLO, that way downstream consumers
have to build error handling in.

### SRE is not an excuse for your developers not to be on call
SRE "guiding czars"

### Measuring deploys is always the wrong metric
If you don't deploy to production often you can also measure on another
environment.

At Google, deploying a feature is a separate task from activating it. They
deploy dead code *a lot*.



