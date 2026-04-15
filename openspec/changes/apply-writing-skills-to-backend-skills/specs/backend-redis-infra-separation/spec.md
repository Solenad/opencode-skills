## ADDED Requirements

### Requirement: Redis concern classification is explicit and enforceable
The backend-redis-infra-separation skill SHALL define explicit classification between application behavior concerns and infrastructure concerns.

#### Scenario: Redis concerns are classified before guidance
- **WHEN** a Redis-related request is analyzed
- **THEN** the skill requires classification as application behavior, infrastructure, or split concern
- **AND** routing guidance follows the classification outcome

#### Scenario: Separation violations are blocked with stop conditions
- **WHEN** infrastructure guidance appears in application behavior context
- **THEN** the skill identifies the violation as a red flag
- **AND** it requires halt-and-reroute before continuation

### Requirement: Handoff requirements are documented
The backend-redis-infra-separation skill SHALL define explicit handoff expectations for cross-boundary dependencies.

#### Scenario: Cross-boundary assumptions are surfaced
- **WHEN** app behavior depends on infra capabilities
- **THEN** the skill requires documenting the assumption and handoff expectations
- **AND** it avoids embedding provisioning steps in app-layer guidance
