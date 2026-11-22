# Job requirements — VMware to OpenShift Virtualization program

Architect-authored job specifications for the migration program, expanded from the source briefs and aligned with market practice for OpenShift Virtualization / KubeVirt platform engineering and SRE observability roles.

| # | Role | Detailed spec (MD) | Hiring posting (MD) | PDF |
| --- | --- | --- | --- | --- |
| 1 | OpenShift Virtualization Platform Engineer | [01-…platform-engineer.md](./01-openshift-virtualization-platform-engineer.md) | [Job Posting](./OpenShift_Virtualization_Platform_Engineer_Job_Posting.md) (LinkedIn-style) | [PDF](./pdf/OpenShift_Virtualization_Platform_Engineer_Job_Posting.pdf) |
| 2 | SRE / Observability Engineer | [02-…observability-engineer.md](./02-sre-observability-engineer.md) | [Job Posting](./SRE_Observability_Engineer_Job_Posting.md) (careers-site style) | [PDF](./pdf/SRE_Observability_Engineer_Job_Posting.pdf) |

### PDF pack (`pdf/`)

- [OpenShift_Virtualization_Platform_Engineer_Job_Posting.pdf](./pdf/OpenShift_Virtualization_Platform_Engineer_Job_Posting.pdf)
- [SRE_Observability_Engineer_Job_Posting.pdf](./pdf/SRE_Observability_Engineer_Job_Posting.pdf)
- [OpenShift_Virtualization_Platform_Engineer_Roles_Responsibilities.pdf](./pdf/OpenShift_Virtualization_Platform_Engineer_Roles_Responsibilities.pdf)
- [SRE_Observability_Engineer_Roles_Responsibilities.pdf](./pdf/SRE_Observability_Engineer_Roles_Responsibilities.pdf)
- [OpenShift_Migration_Roles_Responsibilities_Combined.pdf](./pdf/OpenShift_Migration_Roles_Responsibilities_Combined.pdf)

## Program context

- **Source platform:** VMware
- **Target platform:** Red Hat OpenShift Virtualization (KubeVirt)
- **Migration tooling:** Migration Toolkit for Virtualization (MTV)
- **Lifecycle covered:** Foundation → Pilot → Migration waves → Hypercare → Handoff

## Role boundary (summary)

| Concern | Platform Engineer | SRE / Observability |
| --- | --- | --- |
| Destination cluster & virt Operators | Owns | Consumes telemetry |
| MTV Operator readiness (destination) | Owns | Monitors pipeline health |
| Wave cutover execution | Supports (destination faults) | War-room telemetry |
| Dashboards, alerts, SLOs | Consumes | Owns |
| Technical acceptance evidence | Inputs readiness | Owns automation |
| Guest OS / app validation | Collaborates | Collaborates |

## Sources used to deepen the briefs

- Uploaded program briefs (OpenShift Virtualization Platform Engineer; SRE / Observability Engineer)
- Comparable market postings for OpenShift Virtualization administrators/engineers and SRE observability engineers
- Red Hat MTV planning guidance and OpenShift Virtualization architecture / storage considerations (RWX for live migration, CDI, CSI capabilities)
