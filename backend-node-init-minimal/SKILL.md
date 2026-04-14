---
name: backend-node-init-minimal
description: Initializes a minimal Node backend baseline with canonical directories, health endpoints, and lifecycle-safe entrypoint contracts.
compatibility: opencode
tags: [backend, nodejs, bootstrap, scaffold, healthcheck, lifecycle]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Minimal backend initialization module for greenfield repositories.

## Scope

This module defines minimal baseline setup only.

Included:

- canonical directory structure
- base entrypoint contract (`index.ts` or `index.js`)
- liveness/readiness endpoint contract
- deterministic startup and graceful shutdown contract

Excluded by default:

- business/domain routes
- auth/oauth integrations
- optional infrastructure integrations
- heavy non-essential config scaffolding

## Canonical Baseline Structure

```text
controllers/
services/
repositories/
models/
middleware/
routes/
utils/
config/
types/
```

## Base Entrypoint Contract

The base entrypoint must define:

- deterministic startup ordering
- explicit startup failure handling
- graceful shutdown on termination signals
- observable lifecycle logs

## Health Contract

Minimal scaffold must include:

- liveness semantics (process health)
- readiness semantics (traffic readiness, dependency-aware)

## Compatibility Rule

Guidance from this module must not conflict with `backend-core-architecture-contracts` or `backend-runtime-safety-lifecycle`.
