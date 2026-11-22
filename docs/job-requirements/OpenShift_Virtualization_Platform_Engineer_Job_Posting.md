# OpenShift Virtualization Platform Engineer

**Program:** Platform Diversification / VMware to OpenShift Virtualization Migration  
**Location:** Multiple Locations / Hybrid (program delivery sites)  
**Seniority level:** Mid-Senior level  
**Employment type:** Full-time / Contract (as applicable)  
**Industries:** IT Services · Infrastructure · Cloud Platform Engineering

---

## The Opportunity

Join a high-impact team delivering a VMware-to-OpenShift Virtualization migration using the Red Hat Migration Toolkit for Virtualization (MTV). As an **OpenShift Virtualization Platform Engineer**, you will help design, deploy, and operate the **destination** multi-tier Red Hat OpenShift Virtualization environment that receives, runs, and recovers migrated virtual machines.

This role combines platform engineering, KubeVirt virtualization expertise, automation, and infrastructure modernization. You will participate from foundation through pilot, all migration waves, hypercare, and operational handoff—ensuring the target platform is configured, capacity-ready, secure, and stable before waves arrive, and recoverable when faults occur.

---

## How You'll Make an Impact

- Design, deploy, and support Red Hat OpenShift Virtualization (KubeVirt) on the destination platform, including Operator install/configuration, HyperConverged settings, and day-2 lifecycle support.
- Install and configure the Migration Toolkit for Virtualization (MTV) Operator and validate destination-side readiness for VMware providers (provider connectivity, permissions, platform prerequisites).
- Configure namespaces, RBAC, resource quotas, and tenant/wave isolation for virtualization workloads.
- Configure node placement for VMs (labels, taints/tolerations, dedicated virt worker pools) and validate scheduling behavior under load.
- Create and maintain VM templates, instance types, preference sets, and golden-image patterns for common Linux and Windows footprints.
- Configure KubeVirt settings and live-migration policies to support maintenance drains, node failure recovery, and wave operations.
- Partner with Storage and Network engineering to validate storage classes (especially RWX for live migration), CSI snapshot/clone capabilities, DataVolumes/CDI import paths, Multus/NAD secondary networks, and OVN-Kubernetes attachments mapped from VMware networks.
- Translate VMware networking, resource pools, folders/tags, and VM configurations into OpenShift Virtualization / Kubernetes equivalents.
- Validate platform readiness, capacity, and stability before pilot and each production migration wave; publish and gate on a readiness checklist.
- Troubleshoot destination cluster faults and VM runtime failures (PVC/CDI import issues, virt-launcher crashes, scheduling failures, live-migration failures) and support cutover windows as required.
- Build and maintain infrastructure automation and declarative configuration using YAML, Git, GitOps (Argo CD / OpenShift GitOps), Helm/Kustomize, and Ansible where adopted.
- Collaborate with the MTV Migration Engineer, SRE/Observability, Guest Remediation, Security, and PMO during readiness gates, war rooms, and hypercare.
- Create technical documentation, migration destination runbooks, architecture/as-built diagrams, and operational procedures; provide technical leadership and mentoring across the platform track.
- Hand over known-good configuration baselines, capacity model, and L2/L3 runbooks to steady-state operations after hypercare.

---

## Skills That Drive Success

- Experience designing, deploying, and administering Red Hat OpenShift in enterprise environments.
- Hands-on experience with OpenShift Virtualization / KubeVirt (Operators, VirtualMachine/VMI, DataVolumes/CDI, templates, instance types).
- Strong virtualization background (VMware ESXi/vSphere and/or KubeVirt), including networking, placement, and VM lifecycle concepts.
- Experience supporting enterprise-scale virtual machine migrations, ideally with Red Hat MTV / Forklift on the destination side.
- Strong troubleshooting skills across OpenShift cluster, virtualization, networking, and storage layers.
- Proficiency with Kubernetes RBAC, namespaces, scheduling (labels, taints, affinity), YAML, and `oc`/`kubectl`.
- Experience with Operators / OLM and platform lifecycle (install, upgrade, patch, recover).
- Experience implementing infrastructure automation using Ansible, Git, and GitOps practices.
- Ability to partner across storage, network, security, and migration teams under change-control discipline.
- Strong communication skills with the ability to lead technical discussions, document decisions, and mentor engineers.
- Comfort supporting evening/weekend cutover windows during active migration waves.

---

## What Sets You Apart

- Production experience operating OpenShift Virtualization (KubeVirt) at scale.
- Red Hat Certified Specialist in OpenShift Virtualization (or equivalent hands-on depth).
- Red Hat Certified Specialist in OpenShift Administration (EX280), RHCE, or CKA.
- VMware VCP-DCV or strong vSphere administration experience used to accelerate mapping and cutovers.
- Deep experience with ODF/Ceph or enterprise CSI platforms, including RWX design for live migration.
- Advanced OpenShift Virtualization networking (Multus, NMState, OVS/Linux bridges, VLANs, SR-IOV as applicable).
- Experience with bare-metal OpenShift provisioning and out-of-band server management (Redfish, iDRAC, iLO, UCS/Intersight).
- Experience integrating secrets management (Vault/CyberArk), Compliance Operator, and regulated-environment controls.
- Experience mentoring technical teams and leading complex infrastructure modernization initiatives.
- Prior participation in large VMware-to-OpenShift Virtualization programs (hundreds to thousands of VMs).

---

## Why You'll Love It

- Own the destination platform for a strategic VMware-to-OpenShift Virtualization migration program.
- Work hands-on with OpenShift Virtualization, MTV, and modern GitOps automation—not ticket-only operations.
- Collaborate with a cross-functional tiger team (migration, observability, storage, network, guest remediation).
- Influence architecture, automation, and operational standards that become the BAU platform after handoff.
- Clear ownership: you make the target environment ready to receive, run, and recover migrated VMs.

---

## Role Details

| Field | Value |
| --- | --- |
| Focus | Destination OpenShift Virtualization platform — configuration, stability, recovery |
| Lifecycle | Foundation → Pilot → All migration waves → Hypercare → Operational handoff |
| Partners with | Lead OpenShift Architect; MTV Migration Engineer; SRE/Observability; Storage; Network; Guest Remediation |
| Manages people | No |
| Travel / off-hours | As required for wave cutovers and war rooms |

---

## What Success Looks Like

- Destination clusters pass platform readiness before each pilot/wave gate.
- Migrated VMs schedule, start, and remain available per agreed SLOs.
- Live migration and node maintenance stay within agreed impact thresholds.
- Cluster/VM runtime faults are diagnosed and cleared with clear RCA shared to the program.
- Configuration and runbooks are complete enough for BAU ops to operate without the migration tiger team.

---

## How to Apply

Please apply with a resume that shows **hands-on** Red Hat OpenShift and OpenShift Virtualization experience, including Operator installation and configuration, RBAC and namespace design, VM templates and instance types, live-migration configuration, and concrete examples of cluster or VM runtime incident resolution. Include environment scale (nodes, VM count), storage/network stack, and any VMware→OpenShift Virtualization / MTV exposure.
