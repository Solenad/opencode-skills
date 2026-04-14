---
name: backend-runtime-safety-lifecycle
description: Defines runtime lifecycle safety, health semantics, dependency criticality, and operational baseline for defensive backends.
compatibility: opencode
tags: [backend, runtime, lifecycle, healthcheck, reliability, operations]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Runtime safety module for Node.js + TypeScript + Express services.

## Lifecycle Contract

Define deterministic startup ordering for critical dependencies before accepting traffic.

Recommended pattern:

```text
init critical dependencies -> configure middleware -> register routes -> start listeners/workers
```

On shutdown (`SIGTERM`, `SIGINT`), require graceful closure:

```text
stop timers/workers -> close external clients/pools -> exit with observable logs
```

## Dependency Criticality Matrix

Classify dependencies explicitly:

- Fail-fast critical (service must not run without it)
- Degrade-and-warn optional (service may run with reduced capability)

Production policy should be stricter than local/dev policy; avoid silent unsafe fallbacks.

## Health Semantics (Required)

- Liveness: process is alive; avoid deep dependency checks.
- Readiness: service is ready for traffic based on required dependencies.

If optional dependencies are not configured, readiness behavior must be explicit and observable (warning/telemetry).

## Operational Safety Baseline

Require all of the following:

- Rate limiting for externally reachable endpoints
- DI-friendly composition boundaries
- Liveness/readiness endpoints
- Compression strategy for response efficiency

## Observability Expectations

- Startup phase logs should identify dependency state.
- Shutdown logs should confirm timer/worker and connection closure.
- Degraded modes must emit explicit warning signals.
