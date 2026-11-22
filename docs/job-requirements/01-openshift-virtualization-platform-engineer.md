# OpenShift Virtualization Platform Engineer

**Program:** VMware → OpenShift Virtualization migration (Migration Toolkit for Virtualization / MTV)  
**Role type:** Hands-on platform engineer (destination cluster owner)  
**Lifecycle:** Foundation → Pilot → All migration waves → Hypercare → Operational handoff  
**Reports to / partners with:** Lead OpenShift Architect; MTV Migration Engineer; Storage/Network; Guest Remediation; SRE / Observability

---

## 1. Role overview

The OpenShift Virtualization Platform Engineer owns the **target environment** that receives, runs, and recovers migrated virtual machines. This is not a pure migration-wave operator role: the engineer makes the destination cluster **configured, capacity-ready, secure, and operationally stable** before waves arrive, and restores platform/VM runtime health when faults occur.

Acting under the Lead OpenShift Architect’s standards, the engineer implements OpenShift Virtualization (KubeVirt), CDI, MTV Operators, RBAC/namespaces, node placement, templates/instance types, live-migration policies, and the day-2 operating model required for production VM hosting on OpenShift.

### Mission outcomes

| Outcome | Definition of done |
| --- | --- |
| Platform ready | OpenShift Virtualization + MTV Operators installed, validated, and documented before pilot |
| Wave-ready capacity | Node, storage (RWX where required), network, and quota posture proven for each wave |
| Recoverable VMs | Live migration, snapshots/clones (as designed), and runbooks restore VM service within agreed SLOs |
| Handoff-ready | Config-as-code, SOPs, and known-good baselines transferred to steady-state operations |

---

## 2. Scope of ownership

### Owns

- OpenShift Virtualization Operator, KubeVirt control plane, CDI, and related CRs
- MTV Operator readiness on the **destination** (provider connectivity, permissions, and platform prerequisites—not wave cutover execution owned by MTV Migration Engineer)
- Namespaces, RBAC, SCCs / security context constraints alignment for VM workloads
- VM templates, instance types, preference sets, and golden image pipeline
- Node labeling, taints/tolerations, and VM placement strategy
- Live-migration policies and eviction/maintenance behavior
- Cluster and VM-runtime fault resolution affecting the virtualization platform
- Platform configuration documentation, GitOps/IaC where adopted, and operational runbooks

### Does not own (collaborates with)

| Area | Primary owner |
| --- | --- |
| Migration plan execution, wave cutovers, source inventory orchestration | MTV Migration Engineer |
| Guest OS remediation, agents, app validation inside guests | Guest Remediation |
| Metrics/logs/alerts, acceptance evidence automation | SRE / Observability Engineer |
| Enterprise storage fabric / SAN design | Storage Engineering |
| DC network, firewalls, load balancers | Network Engineering |
| Target architecture standards, non-functional requirements | Lead OpenShift Architect |

---

## 3. Detailed responsibilities

### 3.1 Foundation (platform build)

1. Install and configure **OpenShift Virtualization** and dependent Operators (KubeVirt, CDI, related services) per architecture standards.
2. Install and configure the **Migration Toolkit for Virtualization (MTV)** Operator and validate destination-side readiness for VMware providers.
3. Establish virtualization namespaces, project structure, resource quotas, and limit ranges aligned to tenant/wave models.
4. Implement RBAC for platform admins, migration operators, app owners, and read-only auditors.
5. Configure **node placement** for VM workloads (worker pools, CPU manager / NUMA considerations as required, dedicated virt nodes if designed).
6. Define and publish **VM templates**, **instance types**, and preference sets for common Linux/Windows footprints.
7. Configure KubeVirt HyperConverged / feature gates and cluster-level settings required by the program (e.g., live migration, snapshot support).
8. Validate storage classes used by DataVolumes/PVCs—especially **RWX** for live migration—and confirm CSI snapshot/clone/expansion capabilities with Storage.
9. Validate VM networking model (default pod network, Multus/NAD, OVN-Kubernetes, NMState) with Network for mapped VMware port groups / VLAN equivalents.
10. Produce a **platform readiness checklist** (Operators healthy, capacity headroom, security baselines, backup/DR assumptions documented).

### 3.2 Pilot

1. Harden templates and instance types based on pilot findings.
2. Tune live-migration policies (bandwidth, completion timeouts, auto-converge / post-copy posture as approved).
3. Resolve platform blockers discovered during first MTV plans (permissions, storage mapping gaps, network attachment defects, scheduling failures).
4. Partner with SRE/Observability to confirm virt-layer signals are visible before production waves.
5. Document pilot lessons into SOPs and update GitOps/config baselines.

### 3.3 Migration waves

1. Pre-wave: confirm cluster health, free capacity (CPU/memory/storage IOPS/throughput), Operator status, and node readiness.
2. Ensure destination namespaces, RBAC, NetworkAttachmentDefinitions, and storage classes match the wave’s mapping design.
3. Support wave execution by remediating **destination** faults (pending PVCs, CDI import failures, virt-launcher crashes, scheduling / live-migration failures).
4. Maintain VM lifecycle readiness: start/stop, clone, snapshot (if in scope), live migrate, and recover stuck VirtualMachine / VirtualMachineInstance objects.
5. Participate in war-room triage for cluster-impacting incidents; restore platform stability so waves can continue.
6. Track configuration drift; keep destination environment consistent across waves.

### 3.4 Hypercare and handoff

1. Stabilize recurring VM runtime issues; drive permanent fixes (placement, storage class choice, network config, Operator settings).
2. Finalize runbooks for L2/L3 operations: Operator upgrade notes, VM troubleshooting trees, live-migration failure recovery.
3. Hand over config-as-code, known-good CR examples, capacity model, and open risks to steady-state platform ops.
4. Support knowledge transfer sessions for operations and application owners.

---

## 4. Technical responsibilities by domain

### Compute & scheduling

- Design VM node pools and placement rules; prevent noisy-neighbor and overcommit surprises where policy forbids them
- Configure CPU/memory requests/limits patterns via instance types; advise on hugepages / dedicated CPU where required
- Operate and troubleshoot live migration during node drain, maintenance, and failure scenarios

### Storage (with Storage Engineering)

- Ensure DataVolume / PVC patterns match CSI capabilities (RWO vs RWX, block vs filesystem)
- Validate import paths used by MTV/CDI; troubleshoot CDI pods, scratch space, and incomplete imports
- Align snapshot/clone usage with backup and rapid rollback designs

### Networking (with Network Engineering)

- Implement and validate Multus NADs / secondary networks for migrated VMs
- Troubleshoot VM connectivity, DNS, routes, and NetworkPolicy interactions
- Support mapping of VMware networks to OpenShift Virtualization attachments

### Security & compliance

- Enforce least-privilege RBAC; isolate tenants/waves via namespaces and NetworkPolicies as designed
- Align SCCs, image/pull policies, and secrets handling for VM credentials and cloud-init
- Support hardening baselines (e.g., CIS / organizational policy) without breaking virt Operators

### Automation & documentation

- Prefer declarative config (YAML, Helm, Kustomize, OpenShift GitOps/Argo CD, Ansible) for repeatability
- Maintain SOPs, readiness checklists, and change records for Operator upgrades and policy changes
- Provide clear as-built documentation for handoff

---

## 5. Required skills and experience

### Must-have (hands-on)

- Red Hat OpenShift Container Platform administration (4.x)
- OpenShift Virtualization / KubeVirt (Operators, VirtualMachine, VMI, DataVolume)
- Kubernetes RBAC, namespaces, scheduling (labels, taints, affinity)
- YAML and `oc` / `kubectl` for day-to-day operations
- Operator lifecycle (OLM / OperatorHub) install, upgrade, and troubleshooting
- VM lifecycle on KubeVirt: templates, instance types, live migration
- Strong incident troubleshooting across cluster + virt-launcher + storage/network layers

### Strongly preferred

- Migration Toolkit for Virtualization (MTV / Forklift) destination-side configuration
- OpenShift Data Foundation (ODF) / Ceph or enterprise CSI platforms used with RWX
- Multus, OVN-Kubernetes, NMState, SR-IOV (as applicable)
- GitOps (Argo CD / OpenShift GitOps), Ansible Automation Platform
- Prior VMware vSphere familiarity (enough to collaborate on mappings and cutovers)
- Linux administration; Windows guest awareness for virtio drivers / guest tools expectations

### Nice to have

- Red Hat certifications (EX280, EX370, or equivalent experience)
- Performance tuning for dense VM packing on bare metal OpenShift
- Backup/DR tooling integration for OpenShift Virtualization workloads

---

## 6. Experience profile

| Dimension | Target |
| --- | --- |
| Overall IT / infrastructure | 6–10+ years |
| OpenShift / Kubernetes platform | 3–5+ years hands-on |
| Virtualization (KubeVirt, RHV, or VMware) | 3+ years |
| Production ownership | Experience supporting production clusters and incident response |

---

## 7. Success criteria

- Destination clusters pass platform readiness before each pilot/wave gate
- Migrated VMs schedule, start, and remain available per agreed SLOs
- Live migration and node maintenance do not cause unplanned outages beyond agreed thresholds
- Cluster/VM runtime faults are diagnosed and cleared with clear RCA notes shared to the program
- Configuration and runbooks are complete enough that steady-state ops can operate without the migration tiger team

---

## 8. Working model

- Embedded in the migration program’s platform track; participates in architecture reviews, wave readiness gates, and incident bridges
- Daily collaboration with MTV Migration Engineer on destination blockers
- Escalation path to Lead OpenShift Architect for design deviations and risk acceptance
- Availability aligned to wave cutover windows (may include off-hours during active waves)

---

## 9. How to apply

Submit a resume that demonstrates **hands-on** Red Hat OpenShift and OpenShift Virtualization experience, including:

- Operator installation and configuration (Virtualization / MTV)
- RBAC and namespace design for VM workloads
- VM templates, instance types, and live-migration configuration
- Concrete examples of cluster or VM runtime incident resolution

Include environment scale (nodes, VM count), storage/network stack, and any VMware→OpenShift Virtualization migration exposure.
