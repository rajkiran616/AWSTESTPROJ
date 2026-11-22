# SRE / Observability Engineer (OpenShift Virtualization)

**Program:** Platform Diversification / VMware to OpenShift Virtualization Migration  
**Locations:** Onsite / Hybrid — program delivery locations (Multiple Locations)  
**Job type:** Full-time / Contract (as applicable)

---

## Job Description

We are hiring an SRE / Observability Engineer to establish monitoring, logging, alerting, and operational visibility for our VMware-to-OpenShift Virtualization migration program. You will own migration telemetry, detect infrastructure and virtual machine (VM) health issues early, support rapid fault isolation, and generate technical evidence for migration acceptance.

This role engineers and operates observability for Red Hat OpenShift and OpenShift Virtualization (KubeVirt), including Migration Toolkit for Virtualization (MTV) pipelines, storage and network health signals, and destination VM availability. You will work closely with the OpenShift Virtualization Platform Engineer, MTV Migration Engineer, storage and network teams, guest remediation, and program leadership.

This is an SRE and platform observability role—not an application development role. The focus is keeping migration and destination-platform health **visible, actionable, and evidence-backed** as waves scale. The ideal engineer is hands-on, comfortable owning production incidents end to end, picks up new OpenShift/KubeVirt signals quickly, and can lead cross-functional war-room work to get things done.

You will participate from platform foundation through pilot, production migration waves, hypercare, and steady-state operational handoff.

---

## Responsibilities

- Instrument OpenShift clusters, KubeVirt / OpenShift Virtualization, MTV, storage, and network components for monitoring and logging.
- Configure and maintain Prometheus (including OpenShift Monitoring / User Workload Monitoring), Grafana dashboards, and Alertmanager routing for the migration program.
- Implement alerts for migration failures, transfer throughput, capacity, node pressure, PVC/storage faults, and VM availability.
- Monitor migration pipelines and identify performance bottlenecks before they impact wave cutovers.
- Collect and analyze logs, metrics, Kubernetes Events, and Operator conditions to support incident triage and root-cause analysis.
- Define and monitor service-level indicators/objectives (SLIs/SLOs) and relevant operational indicators for migration and destination VM health.
- Build dashboards for migration progress, infrastructure health, virt-layer health, and workload availability (war-room, engineering, and leadership views).
- Automate monitoring-as-code, reporting, and technical acceptance evidence collection for wave sign-off.
- Provide technical acceptance evidence packages and operational handover documentation to BAU operations.
- Collaborate with platform, migration, storage, and network engineering teams during readiness gates and active waves.
- Support platform foundation, pilot migrations, production migration waves, and hypercare; retune alerts for steady-state after handoff.
- Create and maintain observability runbooks, including a standard “first-look” triage order for migration war rooms.
- Continuously reduce alert noise and improve signal quality as migration scale grows.
- Mentor engineers on observability standards and drive consistent telemetry practices across the program.

---

## Required Qualifications

- Bachelor’s or Master’s degree in Computer Science, Information Systems, related field, or equivalent experience.
- 5–8+ years of SRE, systems, platform, or infrastructure monitoring experience supporting production environments.
- Hands-on experience with Red Hat OpenShift monitoring (Prometheus, Alertmanager, Grafana) in production.
- Experience with logging platforms (OpenShift Logging / Loki, Elasticsearch/OpenSearch, Splunk, or equivalent) and Kubernetes Events analysis.
- Strong troubleshooting skills using metrics, logs, and events to isolate failures across cluster, storage, network, and workload layers.
- Experience defining or operating SLIs/SLOs, capacity analysis, and incident triage / war-room support.
- Scripting and automation experience with Python, Bash, or similar; ability to automate evidence/reporting workflows.
- Working knowledge of Kubernetes/OpenShift fundamentals (`oc`/`kubectl`, namespaces, Operators, resource pressure concepts).
- Experience working in Agile delivery environments and collaborating across infrastructure and application teams.
- Demonstrated ability to own production issues end to end and influence stakeholders during incidents.

---

## Desired Qualifications

- Experience monitoring KubeVirt / OpenShift Virtualization (virt-launcher, DataVolumes/CDI, live migration signals).
- Familiarity with Migration Toolkit for Virtualization (MTV / Forklift) objects, failure modes, and transfer metrics.
- Experience supporting large migration, cutover, or transformation programs with live war-room telemetry.
- Experience with OpenTelemetry and/or enterprise APM tools (e.g., Dynatrace, Splunk Observability) alongside Prometheus/Grafana.
- Experience with GitOps / monitoring-as-code (Argo CD, Helm, Jsonnet, Grafana provisioning).
- Prior VMware monitoring exposure (vCenter / vRealize Operations) and ability to map legacy signals to OpenShift Virtualization.
- Experience delivering technology solutions in large, complex, regulated organizations.
- Strong collaboration skills and ability to quickly learn emerging platform technologies.
- Configuration management or infrastructure-as-code experience (Ansible, Terraform, or similar).

---

## Skills

- Site Reliability Engineering
- OpenShift / Kubernetes Observability
- Prometheus / Grafana / Alertmanager
- Logging & Event Correlation
- SLI / SLO Design
- Incident Response
- Capacity Analysis
- Automation & Scripting
- Migration Telemetry
- Technical Acceptance Evidence
- Collaboration
- Result Orientation
- Analytical Thinking
- Solution Design
- Risk Awareness

---

## Role Details

| Field | Value |
| --- | --- |
| Shift | 1st shift (with off-hours support during active migration waves) |
| Manages people | No |
| Travel | As required for wave cutovers / war rooms (estimate up to 10%) |
| Lifecycle participation | Foundation → Pilot → All migration waves → Hypercare → Steady-state handoff |
| Reports / partners with | Lead OpenShift Architect; OpenShift Virtualization Platform Engineer; MTV Migration Engineer; Storage/Network; Guest Remediation; PMO |

---

## What Success Looks Like

- Infrastructure and VM-health issues are flagged early, before they affect a migration.
- Faults are isolated rapidly using the logs, metrics, dashboards, and alerts this role provides.
- Technical acceptance is supported by automated evidence, not manual collection.
- Alert noise remains low enough that the war room trusts the signal.
- Observability assets and runbooks transfer cleanly to BAU operations after handoff.

---

## How to Apply

Please apply with a resume that shows hands-on OpenShift monitoring and SRE/observability delivery, including Prometheus rules, Grafana dashboards, Alertmanager routing, logging/event analysis used in real incidents, and any KubeVirt, VM, or data-migration telemetry experience. Include cluster scale, tooling stack, and a brief example of an incident you helped isolate with telemetry.
