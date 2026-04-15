## ADDED Requirements

### Requirement: Runtime safety guidance includes defensive enforcement
The backend-runtime-safety-lifecycle skill SHALL include rationalization counters, RED-GREEN-REFACTOR structure, and explicit safety red flags.

#### Scenario: Safety compromises are preempted
- **WHEN** the backend-runtime-safety-lifecycle skill is reviewed
- **THEN** it contains a rationalization table for startup, health, and shutdown shortcuts
- **AND** it maps each shortcut to a corrective safety reality

#### Scenario: Lifecycle decisions are structured and testable
- **WHEN** the backend-runtime-safety-lifecycle skill is reviewed
- **THEN** it contains RED-GREEN-REFACTOR phases for lifecycle contract, health semantics, and cleanup verification
- **AND** each phase includes trigger, action, and verification criteria

### Requirement: Dependency criticality handling is explicit
The backend-runtime-safety-lifecycle skill SHALL provide decision guidance for critical vs optional dependencies, with clear readiness and degradation behavior.

#### Scenario: Criticality decisions are visualized and enforceable
- **WHEN** dependency policy is defined
- **THEN** the skill provides a flowchart or equivalent decision model for fail-fast vs degrade-and-warn
- **AND** red flags include missing graceful shutdown and missing health endpoints
