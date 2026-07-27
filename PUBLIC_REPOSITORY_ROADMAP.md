# SteadyOps Public Engineering Repository Roadmap

SteadyOps public repositories are small, reusable reliability tools rather than article mirrors. Every repository must solve one operational problem, include evidence-oriented output, and remain safe to evaluate outside production.

## Release contract for every repository

A repository is ready for public release only when it has:

- one clearly defined failure mode and target user;
- a useful checklist, template, or executable utility;
- safe defaults and explicit stop conditions;
- sample input and expected output;
- unit tests for normal, blocked, and invalid paths;
- CI on pull requests and the default branch;
- no embedded credentials, private topology, or customer data;
- a usage guide with limitations;
- MIT license and citation metadata where appropriate;
- tagged release packaging with a SHA-256 checksum;
- a canonical SteadyOps implementation guide when a longer explanation exists.

## Released foundations

| Repository | Tested capability |
|---|---|
| `kubernetes-rollback-checklist` | Read-only Kubernetes rollout evidence collector plus rollback decision and evidence templates. |
| `disaster-recovery-runbook-template` | Deterministic 0–20 DR readiness score CLI plus runbook, drill, timeline, and validation templates. |
| `zero-downtime-deployment-checklist` | Deterministic release safety gate plus release checklist and evidence record. |

## Priority 1 — PostgreSQL Failover Drill Kit

Proposed repository: `postgresql-failover-drill-kit`

Planned value:

- read-only Patroni cluster, PostgreSQL replication, PgBouncer, and HAProxy preflight;
- connection budget and replication-lag evidence;
- failover and switchover decision checklist;
- isolated Docker Compose lab for destructive integration tests;
- recovery-point and application-reconnect validation report;
- commands that mutate state available only inside the disposable lab.

The production-facing utility must remain read-only. CI should run the disposable lab and prove the report generator against known healthy and degraded scenarios.

## Priority 2 — Kubernetes Production Readiness Kit

Proposed repository: `kubernetes-production-readiness-kit`

Planned value:

- static inspection of Deployment, StatefulSet, Service, Ingress, PDB, HPA, and NetworkPolicy manifests;
- checks for requests/limits, probes, topology spread, disruption budgets, graceful termination, and rollout strategy;
- evidence-oriented Markdown and JSON reports;
- fixture-based tests with known pass, warning, and block manifests;
- no cluster mutation.

## Priority 3 — SLO and Alert Readiness Audit

Proposed repository: `slo-alert-readiness-audit`

Planned value:

- validate Prometheus alert rules and recording rules;
- identify missing `for` windows, absent runbook URLs, duplicate alerts, fragile labels, and likely high-cardinality patterns;
- map alerts to latency, traffic, errors, saturation, and business-flow coverage;
- generate a review report suitable for an SRE backlog.

## Priority 4 — GitHub Actions Runner Hardening Audit

Proposed repository: `github-actions-runner-hardening-audit`

Planned value:

- inspect workflow permissions, secret exposure boundaries, unpinned third-party actions, artifact retention, concurrency, and self-hosted runner usage;
- produce SARIF or Markdown findings;
- test against intentionally vulnerable workflow fixtures;
- read-only repository analysis.

## Priority 5 — Nginx Zero-Downtime Reload Test

Proposed repository: `nginx-zero-downtime-reload-test`

Planned value:

- disposable Docker-based Nginx test environment;
- continuous-request probe during config validation and reload;
- connection-error, latency, and response-consistency report;
- invalid-config and upstream-failure test scenarios;
- no assumptions about access to a production Nginx host.

## Priority 6 — Incident Evidence Bundle

Proposed repository: `incident-evidence-bundle`

Planned value:

- timestamped collection plan for deployment, Kubernetes, PostgreSQL, Nginx, DNS, TLS, monitoring, and application evidence;
- pluggable read-only collectors;
- automatic redaction tests for tokens, credentials, internal hosts, and customer identifiers;
- archive manifest and SHA-256 checksum;
- explicit warning that evidence collection must not destroy or alter incident state.

## Publication cadence

- Create no more than one new public engineering repository per month.
- Prefer improving and releasing existing repositories between new launches.
- Do not create an empty repository for a planned topic.
- Open the repository only when the first tested utility, documentation, examples, and CI are ready together.
- Publish a canonical SteadyOps article before or alongside the repository when the topic needs a detailed implementation guide.
