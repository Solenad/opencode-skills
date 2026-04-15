## ADDED Requirements

### Requirement: Architecture contract guidance is hardened
The backend-core-architecture-contracts skill SHALL include defensive sections that prevent boundary erosion through explicit rationalization counters and STOP conditions.

#### Scenario: Boundary violations are proactively countered
- **WHEN** the backend-core-architecture-contracts skill is reviewed
- **THEN** it contains a rationalization table for common architecture excuses
- **AND** it includes explicit violations such as controller business logic and raw datastore leakage

#### Scenario: Boundary decisions are visualized
- **WHEN** the backend-core-architecture-contracts skill is reviewed
- **THEN** it includes a flowchart for controller/service/repository boundary checks
- **AND** the flowchart routes to corrective actions when violations are detected

### Requirement: Contract execution gates are explicit
The backend-core-architecture-contracts skill SHALL include red-flag halt conditions and required prerequisite references.

#### Scenario: Violations trigger immediate halt protocol
- **WHEN** a red-flag condition is present
- **THEN** the skill instructs immediate stop and remediation before continuation
- **AND** prerequisite skills are clearly identified in a REQUIRED BACKGROUND section
