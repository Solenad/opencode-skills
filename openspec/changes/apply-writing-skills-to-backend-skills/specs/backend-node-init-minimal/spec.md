## ADDED Requirements

### Requirement: Minimal bootstrap scope is defensively enforced
The backend-node-init-minimal skill SHALL include rationalization counters and red flags that prevent scope creep beyond baseline initialization.

#### Scenario: Bootstrap overreach is prevented
- **WHEN** backend-node-init-minimal guidance is reviewed
- **THEN** it includes explicit exclusions for business routes, auth integrations, and optional infrastructure setup
- **AND** it includes a red flags section with stop protocol for overreach

#### Scenario: Lifecycle baseline remains mandatory
- **WHEN** backend-node-init-minimal guidance is reviewed
- **THEN** it enforces liveness/readiness semantics and graceful shutdown as required baseline
- **AND** it does not mark these as optional for prototypes

### Requirement: Compatibility dependencies are explicit
The backend-node-init-minimal skill SHALL explicitly reference required companion skills for architecture and lifecycle consistency.

#### Scenario: Bootstrap dependencies are clearly stated
- **WHEN** metadata and body are reviewed
- **THEN** the skill declares required references to backend-core-architecture-contracts and backend-runtime-safety-lifecycle
- **AND** it includes a REQUIRED BACKGROUND section for prerequisite loading
