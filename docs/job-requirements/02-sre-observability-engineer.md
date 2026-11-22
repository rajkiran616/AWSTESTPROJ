# SRE / Observability Engineer

**Program:** VMware → OpenShift Virtualization migration (Migration Toolkit for Virtualization / MTV)  
**Role type:** SRE / observability engineer (migration telemetry, early warning, acceptance evidence)  
**Lifecycle:** Foundation → Pilot → All migration waves → Hypercare → Steady-state handoff  
**Reports to / partners with:** Lead OpenShift Architect; OpenShift Virtualization Platform Engineer; MTV Migration Engineer; Storage/Network; Guest Remediation; Program PMO

---

## 1. Role overview

The SRE / Observability Engineer makes **migration health visible in real time**. The engineer instruments the destination platform and migration path, builds dashboards and alerts that provide early warning, supports rapid fault isolation with the right telemetry, and automates **technical acceptance evidence** so wave sign-off is data-backed—not manual screenshot collection.

This role sits at the intersection of OpenShift platform monitoring, KubeVirt/VM health, MTV pipeline telemetry, and SRE practice (SLIs/SLOs, error budgets, incident support, toil reduction).

### Mission outcomes

| Outcome | Definition of done |
| --- | --- |
| Early warning | Infra and VM-health issues are flagged before they fail a migration wave |
| Fast isolation | On-call / war-room can locate failing layer (cluster, storage, network, MTV, VM) from dashboards + logs within minutes |
| Evidence-based acceptance | Technical acceptance packs are generated automatically per wave/VM cohort |
| Operable handoff | Monitoring, alert routing, runbooks, and SLO definitions transfer cleanly to BAU ops |

---

## 2. Scope of ownership

### Owns

- Instrumentation strategy for OpenShift cluster, KubeVirt, MTV, storage, and network health signals relevant to migration
- Prometheus / User Workload Monitoring rules, Grafana dashboards, Alertmanager routing for the program
- Logging and event correlation patterns used during migration incidents (OpenShift Logging / Loki or enterprise stack as adopted)
- SLI/SLO definitions for migration and destination VM availability/performance (as agreed with Architect / PMO)
- Automation that produces technical acceptance evidence (reports, exports, compliance artifacts)
- Observability runbooks and “what to look at first” triage guides for migration war rooms

### Does not own (collaborates with)

| Area | Primary owner |
| --- | --- |
| Cluster Operator install, VM templates, live-migration policy | OpenShift Virtualization Platform Engineer |
| MTV wave planning, cutover execution, plan objects | MTV Migration Engineer |
| Guest OS / application functional validation | Guest Remediation / App owners |
| Enterprise APM product selection (if corporate standard) | Enterprise Observability / Architect |
| Business go/no-go decisions | Program leadership |

---

## 3. Detailed responsibilities

### 3.1 Foundation (instrumentation baseline)

1. Establish monitoring coverage for OpenShift control plane and worker health used by virtualization nodes.
2. Instrument **KubeVirt / OpenShift Virtualization** signals: virt-operator, virt-api, virt-controller, virt-handler, virt-launcher, CDI, DataVolume states.
3. Instrument **MTV / Forklift** pipeline health: provider connectivity, plan progress, transfer errors, stuck migrations.
4. Instrument **storage** signals critical to VM disks and imports (PVC pending, CSI errors, latency/IOPS where available, ODF/Ceph or vendor metrics).
5. Instrument **network** signals relevant to VM attachment and migration throughput (node network saturation, CNI errors, secondary network health where exposed).
6. Stand up Grafana dashboard packs: platform health, virt health, MTV transfer, capacity/node pressure, VM availability.
7. Define Alertmanager routes for migration war-room channels vs. platform on-call; tune for signal-to-noise.
8. Document telemetry architecture, metric names, log queries, and ownership.

### 3.2 Pilot

1. Validate that pilot failures are **detectable** (missing metrics = defect in observability, not just in platform).
2. Calibrate alert thresholds using pilot baselines (transfer throughput, cutover duration, node pressure).
3. Build first version of **technical acceptance evidence** automation (pre/post checks, VM running state, disk attach, basic health probes).
4. Produce a pilot observability retrospective: blind spots, noisy alerts, missing labels/dimensions.
5. Lock a “minimum observability gate” required before production waves.

### 3.3 Migration waves

1. Provide live dashboards during wave execution (throughput, errors, queue depth, capacity headroom, VM up/down).
2. Emit early warnings for node pressure, storage saturation, API server / etcd stress, and MTV error spikes.
3. Support incident triage: collect and package metrics, logs, Kubernetes events, and Operator conditions for RCA.
4. Track wave-level SLIs (e.g., % VMs migrated successfully, mean transfer rate, cutover duration, time-to-detect, time-to-mitigate).
5. Generate per-wave acceptance evidence packages for technical sign-off.
6. Continuously reduce alert noise; add recording rules / aggregations as scale grows.

### 3.4 Hypercare and handoff

1. Retune alerts for steady-state VM hosting (vs. migration-centric alerts).
2. Finalize SLO dashboards and error-budget views for destination virtualization services.
3. Hand over dashboard JSON / GitOps, alert rules, runbooks, and evidence tooling to BAU SRE/ops.
4. Document known gaps and recommended next-phase observability investments (tracing, OpenTelemetry adoption, long-term retention).

---

## 4. Technical responsibilities by domain

### Metrics (Prometheus ecosystem)

- Use OpenShift Monitoring and User Workload Monitoring appropriately; avoid breaking platform Prometheus contracts
- Create PromQL recording/alerting rules for MTV, KubeVirt, node pressure, PVC health, and VM availability
- Capacity analysis: CPU/memory headroom, storage growth, concurrent migration limits

### Visualization (Grafana)

- Build role-oriented views: war-room (live), platform eng (deep dive), leadership (wave progress / risk)
- Standardize labels (cluster, namespace, wave_id, vm_name, storage_class, network) for filterability
- Keep dashboards version-controlled where GitOps is used

### Logging & events

- Define log sources for MTV controllers, CDI, virt-launcher, and critical Operators
- Correlate Kubernetes Events with metric anomalies during incidents
- Provide saved queries / runbook links for common failure modes (import stuck, live migration failed, PVC pending)

### Alerting & incident support

- Design severity model (page vs. ticket vs. war-room channel)
- Support bridge calls with evidence packs; never leave triage without a next data query
- Contribute to post-incident reviews with timeline reconstruction from telemetry

### SLOs & acceptance

- Define SLIs with Architect/PMO (examples below are illustrative—finalize per program):
  - Destination VM availability after cutover
  - MTV plan success rate / retry rate
  - Transfer throughput vs. planned window
  - Time-to-detect platform blockers
- Automate acceptance evidence: VM Running, disks Bound, network interfaces ready, no CrashLoop on virt-launcher, optional guest heartbeat if available
- Store evidence artifacts with wave identifiers for auditability

### Automation

- Script evidence collection and report generation (Python, Bash, or Ansible)
- Automate dashboard/alert deployment (GitOps, Jsonnet/Grafana provisioning, or Helm)
- Reduce toil: replace manual log gathering with one-command triage bundles

---

## 5. Required skills and experience

### Must-have (hands-on)

- SRE or infrastructure observability experience in production environments
- Red Hat OpenShift monitoring stack (Prometheus, Alertmanager, Grafana)
- Logging platforms (OpenShift Logging/Loki, Elasticsearch/OpenSearch, or equivalent enterprise stack)
- Kubernetes Events, metrics, and basic cluster troubleshooting with `oc`
- SLI/SLO thinking and capacity analysis
- Incident triage using logs + metrics (not intuition alone)
- Automation/scripting (Python and/or Bash; Ansible a plus)

### Strongly preferred

- Observability for **KubeVirt / OpenShift Virtualization** and VM lifecycle metrics
- Familiarity with **MTV / Forklift** migration objects and failure modes
- OpenTelemetry instrumentation patterns
- GitOps for monitoring-as-code
- Experience supporting large migration or cutover programs (war-room telemetry)

### Nice to have

- Prior VMware monitoring exposure (vCenter/vROps) to map old signals to new ones
- Distributed tracing (Jaeger/Tempo) for platform services
- Status page / incident tooling integration (PagerDuty, Opsgenie, ServiceNow)

---

## 6. Experience profile

| Dimension | Target |
| --- | --- |
| Overall IT / SRE / monitoring | 5–8+ years |
| Kubernetes / OpenShift observability | 2–4+ years hands-on |
| Prometheus + Grafana | Production rule and dashboard authorship |
| Incident support | Experience in L2/L3 or war-room telemetry roles |

---

## 7. Success criteria

- Infrastructure and VM-health issues are flagged **before** they fail migrations
- Faults are isolated rapidly using this role’s dashboards, alerts, logs, and evidence packs
- Technical acceptance is supported by **automated evidence**, not ad-hoc manual collection
- Alert noise remains low enough that war-room trusts the signal
- BAU operations can run the observability stack without the migration team after handoff

---

## 8. Working model

- Embedded in the migration program’s reliability track; joins readiness gates and active wave bridges
- Partners daily with Platform Engineer (destination health) and MTV Migration Engineer (pipeline health)
- Aligns SLOs and acceptance criteria with Lead OpenShift Architect and PMO
- Availability aligned to wave cutover windows (may include off-hours during active waves)

### Example “first look” triage order (owned as a runbook)

1. Cluster / node pressure and Operator degradations  
2. Storage / PVC / CDI import health  
3. MTV plan / transfer errors  
4. KubeVirt VMI / virt-launcher state  
5. Network attachment / throughput saturation  
6. Guest-level signals (if instrumented)—hand to Guest Remediation

---

## 9. How to apply

Submit a resume that demonstrates hands-on OpenShift monitoring and SRE/observability delivery, including:

- Prometheus rules, Grafana dashboards, and Alertmanager routing you built
- Logging/event analysis used in real incidents
- Any KubeVirt, VM, or data-migration telemetry experience
- Examples of automated reporting or acceptance/evidence tooling

Include cluster scale, tooling stack, and a brief example of an incident you helped isolate with telemetry.
