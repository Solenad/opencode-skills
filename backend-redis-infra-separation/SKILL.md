---
name: backend-redis-infra-separation
description: Enforces clear boundaries and handoff between Redis application behavior guidance and Redis infrastructure operations.
compatibility: opencode
tags: [backend, redis, infra, architecture, boundaries]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Boundary module for Redis concerns.

## Separation Contract

Application-level Redis guidance includes:

- key usage contracts
- lock semantics
- cache consistency/fallback behavior
- session/cache behavior policy in app logic

Infrastructure Redis guidance includes:

- topology/HA design
- persistence and backup strategy
- failover/disaster recovery
- TLS/ACL and platform deployment

Do not merge these concern sets in one implementation plan.

## Handoff Rule

When an app-level pattern depends on infra capabilities, explicitly document assumptions and handoff requirements without embedding provisioning steps.

## Escalation Trigger

If user request includes provisioning, cluster management, security hardening at infra layer, or platform-specific Redis operations, route to dedicated infra skill path.
