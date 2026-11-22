# LinkedIn post (copy-paste ready)

Use the **Primary** version first. **Shorter** is an alternate if you want a tighter ask.

---

## Primary — discussion post

I've been a strong advocate for onboarding applications onto Kubernetes — not because “everyone runs K8s,” but because of what teams inherit once they’re on the platform.

Service discovery by name instead of fragile IPs.  
Shared storage patterns the platform can actually govern.  
An internal path between services — so east–west traffic isn’t a patchwork of one-off proxies.  
And with a service mesh like Istio: security screening closer to the call path, plus mTLS so service-to-service communication is encrypted and authenticated without every app reinventing crypto.

That’s the pitch I keep making internally.

But I’m also honest that this isn’t the only good path.

Plenty of teams ship just fine on managed container platforms — ECS, Fargate, Cloud Run, App Runner, ACI, and the rest — and spend less time operating the control plane.

So I want this post to be a conversation, not a lecture.

If you’re running production workloads today:

→ Are you on Kubernetes, a managed orchestrator (ECS / Fargate / similar), or a mix?  
→ What actually decided it for you — security controls, cost, team skills, multi-cloud, time-to-ship?  
→ Where did the “platform promise” (discovery, shared storage, encrypted internal traffic) show up in real life… and where did it stay a slide?

Drop your perspective in the comments. Especially if you chose *against* Kubernetes on purpose — that’s often the more useful story.

Curious what the community is seeing in 2026.

#Kubernetes #AWS #ECS #Fargate #ServiceMesh #Istio #PlatformEngineering #CloudNative #DevOps

---

## Shorter alternate

Hot take I’m willing to defend: Kubernetes is less about containers and more about what you inherit — service discovery, shared storage discipline, internal service communication, and (with Istio) mTLS + policy without rewriting every app.

Also willing to hear I’m wrong for your context.

Are you on K8s, ECS/Fargate (or another managed container service), or both?

What actually drove the choice — security, cost, skills, or speed?

Comment your stack + the one reason that mattered most. I’ll reply to as many as I can.

#Kubernetes #ECS #Fargate #PlatformEngineering #CloudNative

---

## Posting tips

- Post as a normal LinkedIn update (not a Live / Event).
- First comment (optional): link to your talk outline or ask one follow-up, e.g. “If you use ECS/Fargate, how do you handle service-to-service encryption today?”
- Reply to early comments within the first hour — that’s what keeps the post “living.”
- Avoid starting with a link in the body; put links in the first comment if you share the deck.
