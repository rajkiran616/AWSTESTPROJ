# Kubernetes advocacy talk — key points

**Title:** Kubernetes: Service Discovery, Shared Storage & Secure Service Communication  
**Deck:** open `index.html` in a browser · arrows / space to navigate · `N` for speaker notes

---

## 1. Why onboard applications to Kubernetes

You are not asking teams to “move to containers for fun.” You are asking them to join a **platform** so they inherit shared capabilities:

- One deploy / scale / health model
- Stable internal networking
- Approved storage and secrets patterns
- A single place to attach company security and traffic policy

**Line to say:** *Onboard once. Get discovery, storage, and secure communication for free.*

---

## 2. Service discovery

**Problem:** Hardcoded IPs, per-environment host files, and homemade registries break whenever instances move.

**Kubernetes answer:**

- Every workload gets a **Service** with a stable DNS name
- Selectors keep endpoints updated as pods restart or scale
- Apps call `payments.billing.svc.cluster.local` (or a short name in-namespace) instead of chasing IPs

**Line to say:** *Services find each other by name — not by fragile addresses.*

---

## 3. Shared storage

**Problem:** Teams invent one-off NFS mounts, sidecar sync jobs, or push large artifacts through object storage in inconsistent ways.

**Kubernetes answer:**

- **PersistentVolumeClaims** for durable disks across restarts
- **StorageClasses** so the platform maps teams to approved backends (for example EBS / EFS on AWS)
- **ReadWriteMany** when multiple pods truly need a shared filesystem
- Encryption at rest, capacity, and backup standards live with the platform — not each app

**Caveat worth saying:** most microservices should stay stateless; shared storage is for the cases that genuinely need it.

---

## 4. Internal communication & company proxy

**Problem:** Every department stands up its own reverse proxy, VPN path, or allowlist spaghetti for service-to-service calls.

**Kubernetes answer:**

- **East–west:** service-to-service traffic stays on the cluster / VPC network
- **North–south:** Ingress or API gateway is the controlled front door
- **NetworkPolicies** limit which workloads may talk to which

**Line to say:** *The cluster is our internal company proxy between services — by design.*

---

## 5. Service mesh (Istio) — security screening & policy

**Problem:** App teams cannot uniformly enforce identity, authorization, or traffic rules across languages and frameworks.

**Istio (service mesh) answer:**

- A proxy beside (or around) every workload intercepts calls
- **Workload identity** replaces brittle IP allowlists
- **AuthorizationPolicy** / **PeerAuthentication** = security screening in front of services
- Traffic features (retries, timeouts, canaries, circuit breaking) become platform config

**Line to say:** *Istio is the control layer — security and traffic policy without rewriting every service.*

> Note: in conversation this is often what people mean when they reach for “the mesh” / Istio on top of plain Kubernetes networking.

---

## 6. Data encryption between services (mTLS)

**Problem:** Internal traffic is often plaintext; a single compromised pod can sniff or spoof lateral calls.

**Mesh answer — mutual TLS:**

- Every service hop is **encrypted and mutually authenticated**
- Certificates are issued and rotated by the mesh — apps do not manage PEM files
- Works across stacks; policy is declarative and auditable

**Line to say:** *mTLS means we encrypt and authenticate every hop between services — with less custom crypto in application code.*

---

## Closing ask

1. Pick **one pilot service** to onboard with discovery + NetworkPolicies.
2. Add **Istio mTLS** for that service’s critical dependencies.
3. Pair **platform + security** so policy is owned centrally as more apps land.

**Close:** *Discovery. Storage. Mesh security. Let’s choose the first app we onboard together.*
