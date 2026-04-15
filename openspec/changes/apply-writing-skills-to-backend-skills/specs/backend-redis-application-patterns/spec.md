## ADDED Requirements

### Requirement: Redis application behavior guidance is defensively structured
The backend-redis-application-patterns skill SHALL include rationalization counters, RED-GREEN-REFACTOR sections, and Redis-specific red flags.

#### Scenario: Redis behavior shortcuts are explicitly countered
- **WHEN** the backend-redis-application-patterns skill is reviewed
- **THEN** it contains rationalization entries for fallback policy, lock TTL, ownership verification, and reconciliation
- **AND** each entry includes explicit mitigation guidance

#### Scenario: Redis behavior workflow is phase-based
- **WHEN** the backend-redis-application-patterns skill is reviewed
- **THEN** it includes RED-GREEN-REFACTOR phases for policy definition, consistency implementation, and lock safety verification
- **AND** it defines verification criteria for each phase

### Requirement: Redis app/infrastructure boundary is reinforced
The backend-redis-application-patterns skill SHALL explicitly require the infra-separation companion skill for boundary safety.

#### Scenario: Boundary dependency is explicit
- **WHEN** cross-references are reviewed
- **THEN** the skill includes REQUIRED BACKGROUND guidance that references backend-redis-infra-separation
- **AND** the guidance warns against infra/app conflation
