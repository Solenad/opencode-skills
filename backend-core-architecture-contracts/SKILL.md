---
name: backend-core-architecture-contracts
description: Enforces architecture boundaries, repository DTO contracts, invariant discipline, and error taxonomy for defensive backends.
compatibility: opencode
tags:
  [backend, architecture, layering, dto, invariants, errors, nodets, express]
metadata:
  workflow: openspec-proposal
  priority: correctness-over-speed
  requires: openspec-proposal
---

Canonical architecture contract module for Node.js + TypeScript + Express.

## Enforced Structure

```text
src/
|- controllers/   # HTTP request/response mapping only
|- services/      # Use-case rules, invariants, orchestration
|- repositories/  # Persistence contracts and mapping
|- models/        # Domain models
|- middleware/    # Express middleware
|- routes/        # Route wiring and middleware order
|- utils/         # Pure helpers
|- config/        # App config (excluding DB bootstrap details)
|- types/         # TS contracts
```

Structural deviations require explicit user approval and documented rationale.

## Boundary Model

```text
Route -> Controller -> Service -> Repository -> Datastore
Datastore -> Repository mapper -> Repository DTO -> Service -> Controller response
```

Rules:

- Controllers do not own business rules or persistence logic.
- Services do not return raw datastore row/document shapes.
- Repositories own mapping/normalization and return explicit DTO contracts.

## Repository DTO Contract Rules

- Define DTO contracts for query/filter inputs, mutation inputs, and read outputs.
- Keep nullability explicit and deterministic in output shape.
- Block sensitive/internal fields unless explicitly required by contract.
- Stabilize DTO shape for testability and client compatibility.

## Error Taxonomy (Required)

- Validation failures -> 400/422
- Authentication failures -> 401
- Authorization failures -> 403
- Not found -> 404
- Conflict/invariant violations -> 409
- Unexpected/internal failures -> 500

Apply category mapping consistently per capability.

## Invariant Discipline

For mutating workflows, explicitly define and preserve:

- Referential consistency
- No orphaned dependent records/documents
- Idempotent behavior when required
- Partial-failure handling (transaction, rollback, or compensation)

If invariants cannot be guaranteed by the current approach, pause and revise design artifacts first.

## Common Pitfalls

- Business logic leaking into controllers
- Services coupled to raw datastore output
- Missing null/empty guards
- Inconsistent error category mapping
- Untracked structural deviations that erode maintainability
