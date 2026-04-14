---
name: backend-redis-application-patterns
description: Defines Redis behavior patterns at the backend application layer: locking, cache consistency, fallback, and operability.
compatibility: opencode
tags: [backend, redis, cache, locks, consistency, reliability]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Application-layer Redis behavior module. This skill does not cover Redis provisioning or infrastructure bootstrap.

## Scope

Use this module for:

- cache/session behavior contracts inside backend logic
- lock semantics for distributed single-runner jobs
- consistency/reconciliation behavior between datastore and cache
- fallback policy when Redis is unavailable

## Optional-by-Policy Behavior

Define per capability whether Redis is:

- required (fail-fast)
- optional (degrade-and-warn)

Do not leave behavior implicit.

## Single-Runner Distributed Jobs

When multi-instance workloads need one active runner, require lock-based coordination.

Pattern:

```text
acquire lock (set if absent + TTL) -> run job -> release only if owner
```

Require owner verification before lock release and bounded lock TTL.

## Cache Consistency and Fallback

- Define reconciliation strategy when cache diverges from source-of-truth.
- Define post-commit fallback action if cache update fails (for example, invalidate stale keys).
- Ensure failures are observable and deterministic.

## Operability Expectations

For manual cache maintenance flows, expose progress/status visibility semantics (running/completed/failed with bounded retention).
