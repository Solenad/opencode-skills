---
name: backend-defensive-engineering
description: Orchestrator for modular defensive backend engineering guidance in Node.js + TypeScript + Express projects.
compatibility: opencode
tags: [backend, nodejs, typescript, express, architecture, correctness, modular]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Use this as the entry skill for backend work. It preserves global correctness guardrails and routes to focused companion skills.

## Global Guardrails

- Defensive correctness over speed.
- Proposal-first for non-trivial changes.
- Strict layer boundaries and explicit invariant discipline.
- Repository DTO boundaries at service interfaces.
- Operational safety baseline is mandatory.
- Redis application behavior and Redis infrastructure concerns must remain separated.

## Modular Topology and Ownership

```text
backend-defensive-engineering (orchestrator)
  |- backend-core-architecture-contracts
  |- backend-data-behavior (optional companion)
  |- backend-runtime-safety-lifecycle
  |- backend-auth-session-hardening
  |- backend-redis-application-patterns
  |- backend-redis-infra-separation
  |- backend-node-init-minimal
```

## Delegation Map

Use the following routing rules:

- Architecture boundaries, DTO contracts, invariant taxonomy, error taxonomy -> `backend-core-architecture-contracts`
- Multi-database behavior-level guidance (MySQL/PostgreSQL/MongoDB semantics, no bootstrap wiring) -> `backend-core-architecture-contracts` or dedicated `backend-data-behavior` if present
- Startup/shutdown lifecycle, liveness/readiness, dependency criticality, baseline middleware policy -> `backend-runtime-safety-lifecycle`
- OAuth/session model design, cookie/session policy, session typing, auth failure mapping -> `backend-auth-session-hardening`
- Redis cache/lock/reconciliation/fallback semantics in app behavior -> `backend-redis-application-patterns`
- Redis app-vs-infra boundary and handoff expectations -> `backend-redis-infra-separation`
- Greenfield bootstrap for minimal backend structure and lifecycle-safe base entrypoint -> `backend-node-init-minimal`

## Rule Ownership Matrix

- Layer boundaries and DTO contracts owner -> `backend-core-architecture-contracts`
- Error taxonomy owner -> `backend-core-architecture-contracts`
- Runtime lifecycle and health semantics owner -> `backend-runtime-safety-lifecycle`
- Auth/session policy owner -> `backend-auth-session-hardening`
- Redis app behavior owner -> `backend-redis-application-patterns`
- Redis infra boundary owner -> `backend-redis-infra-separation`
- Minimal greenfield bootstrap owner -> `backend-node-init-minimal`

## Deterministic Precedence

When a request spans multiple modules, apply in this order:

1. `backend-core-architecture-contracts`
2. `backend-runtime-safety-lifecycle`
3. Specialized module(s): auth/session, redis app patterns, node init

This avoids conflicting guidance and keeps rule ownership stable.

## Redis Infra Boundary Rule

If the request concerns topology, provisioning, HA, persistence, backup, TLS/ACL, or deployment platform specifics, route to a dedicated infra skill path and avoid embedding infra setup in app-level modules.

## Proposal-First Gate

For non-trivial changes, ensure proposal/design/spec/tasks are coherent before implementation guidance. If implementation assumptions break, update artifacts first.

## Non-Goals

- This orchestrator does not provide database bootstrap wiring details.
- This orchestrator does not replace specialized companion skill instructions.
