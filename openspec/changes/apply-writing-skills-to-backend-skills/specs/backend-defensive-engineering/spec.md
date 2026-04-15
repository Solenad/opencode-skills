## ADDED Requirements

### Requirement: Defensive orchestration structure is explicit
The backend-defensive-engineering skill SHALL define defensive orchestration sections for rationalization handling, RED-GREEN-REFACTOR guidance, red flags, and required background dependencies.

#### Scenario: Orchestrator includes anti-rationalization structure
- **WHEN** the backend-defensive-engineering skill is reviewed
- **THEN** it contains a rationalization table with explicit excuse-to-reality mappings
- **AND** it includes a red flags section with explicit STOP protocol

#### Scenario: Orchestrator includes workflow and routing clarity
- **WHEN** the backend-defensive-engineering skill is reviewed
- **THEN** it contains a RED-GREEN-REFACTOR section with trigger, action, and verification for each phase
- **AND** it includes at least one flowchart for delegation or precedence decisions

### Requirement: Dependency loading guidance is explicit
The backend-defensive-engineering skill SHALL declare prerequisite and companion skill dependencies in metadata and a REQUIRED BACKGROUND section.

#### Scenario: Orchestrator states required dependencies
- **WHEN** the skill frontmatter and body are reviewed
- **THEN** dependency references are explicit and unambiguous
- **AND** the skill states that routing should not proceed until prerequisites are loaded
