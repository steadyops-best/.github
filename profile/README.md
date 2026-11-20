# SteadyOps

SteadyOps publishes practical DevOps/SRE guides and reusable production-reliability artifacts for teams that need safer releases, tested recovery, clearer ownership, and evidence that operational controls work outside a document.

- Website: https://steadyops.best/
- [DevOps/SRE implementation guides](https://steadyops.best/articles/)
- [Open-source reliability tools and checklists](https://steadyops.best/resources/)
- [Public engineering repository roadmap](https://github.com/steadyops-best/.github/blob/main/PUBLIC_REPOSITORY_ROADMAP.md)

## Public engineering resources

| Repository | Tested utility | What it helps a team prove | Canonical guide |
|---|---|---|---|
| [Kubernetes Rollback Checklist](https://github.com/steadyops-best/kubernetes-rollback-checklist) | Read-only rollout evidence collector with unit tests and CI | A failed rollout can be stopped, reversed, and validated without guessing. | [Kubernetes rollback implementation guide](https://steadyops.best/articles/kubernetes-rollback-checklist-for-production-deployments/) |
| [Disaster Recovery Runbook Template](https://github.com/steadyops-best/disaster-recovery-runbook-template) | Deterministic DR readiness scoring CLI with sample input, tests, and CI | Recovery has owners, stop conditions, measurable RPO/RTO, validation, and drill evidence. | [Disaster recovery runbook guide](https://steadyops.best/articles/ha-dr-runbooks/) |
| [Zero-Downtime Deployment Checklist](https://github.com/steadyops-best/zero-downtime-deployment-checklist) | Deterministic release safety gate with sample input, tests, and CI | Readiness, compatibility, traffic switching, rollback, and release evidence are defined before production change. | [Zero-downtime deployment guide](https://steadyops.best/articles/zero-downtime-bluegreen-deployments/) |

The repositories contain forkable operational files and tested utilities. Pull requests compile the tools and run unit tests. Tagged versions are designed to produce packaged GitHub Releases with SHA-256 checksums. The linked SteadyOps articles remain the maintained implementation guides with failure-mode analysis, configuration examples, validation criteria, official references, and related decision paths.

## Engineering focus

- PostgreSQL high availability, Patroni, PgBouncer, routing, failover, backup, and restore validation
- Kubernetes production readiness, rollout safety, observability, capacity, access, and recovery
- CI/CD release gates, Blue/Green and canary delivery, migration compatibility, and rollback
- Prometheus, Grafana, logs, traces, Sentry, actionable alerts, and SLO-oriented incident response
- disaster recovery, incident command, runbooks, RPO/RTO, and business validation
- named access, SSO, RBAC, secrets, network boundaries, and reviewable security evidence
- Nginx, HAProxy, Docker, Linux, systemd, queues, and customer-facing WebOps
- infrastructure cost and capacity optimization without removing resilience blindly

## How these resources are designed

SteadyOps artifacts follow a consistent operating model:

1. **Start with the failure mode.** Explain what can break and why the control matters.
2. **Name ownership.** Decisions, execution, validation, and escalation need visible owners.
3. **Define stop conditions.** Engineers should know when not to continue.
4. **Use executable steps.** Commands and configuration are paired with expected results and limitations.
5. **Validate customer impact.** Process health alone is not proof that a service recovered.
6. **Retain evidence.** Store timestamps, outputs, decisions, results, and follow-up ownership.
7. **Test before release.** Utilities need sample input, unit tests, CI, and safe defaults before they become public artifacts.
8. **Keep examples adaptable.** Public files use safe placeholders and avoid private topology or credentials.

## Start with the production problem

Use the [PostgreSQL HA and failover review](https://steadyops.best/postgresql-ha-review/) when failover, restore, Patroni, PgBouncer, or routing is uncertain. For other production risks, start with the [SteadyOps reliability case library](https://steadyops.best/reliability-cases/) and choose the closest operating scenario.

For a storefront or booking app, start with the customer flow a release could break. [WebOps Plus for active web apps](https://steadyops.best/webops-plus/) explains what to check around checkout, payments, bookings, and escalation.

## Author and public identity

SteadyOps is led by Yuri Osipov, Founder & Principal DevOps/SRE.

- [Yuri Osipov — SteadyOps profile](https://steadyops.best/team/yuri-osipov/)
- [LinkedIn](https://www.linkedin.com/in/yuri-osipov-0876b0254)
- [GitHub](https://github.com/lNickSoN)
- [Hashnode](https://steadyops.hashnode.dev/)

## Reuse and contribution

Public templates and utilities are MIT-licensed and include citation metadata where applicable. Fork them, replace placeholders, run the tests, validate against the real environment, and keep environment-specific secrets and topology private.

Contributions are welcome when they add a real failure mode, safer precondition, stop condition, validation step, primary reference, test fixture, or evidence output. The repositories intentionally reject vendor marketing, unsupported claims, unrelated SEO links, and dangerous universal commands.
