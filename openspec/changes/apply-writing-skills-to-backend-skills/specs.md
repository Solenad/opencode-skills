## ADDED Requirements

### Requirement: Rationalization tables added to all backend skills
All six backend skills SHALL include Rationalization Tables documenting common objections and explicit refutations.

#### Scenario: backend-defensive-engineering includes rationalization table
- **WHEN** backend-defensive-engineering SKILL.md is loaded
- **THEN** it contains a "Rationalization Table - Common Objections" section with excuse/reality pairs
- **AND** it includes at least 7 common excuses documented
- **AND** each excuse has explicit refutation under "Reality"

#### Scenario: backend-core-architecture-contracts includes architecture violations table
- **WHEN** backend-core-architecture-contracts SKILL.md is loaded
- **AND** it contains a "Rationalization Table - Architecture Violations" section
- **THEN** it documents at least 8 architecture-violation excuses with counterarguments
- **AND** includes "CONTROLLER LOGIC" and "MISSING DTO" as explicit excuses

#### Scenario: backend-runtime-safety-lifecycle includes safety compromises table
- **WHEN** backend-runtime-safety-lifecycle SKILL.md is loaded
- **AND** it contains a "Rationalization Table - Safety Compromises" section
- **THEN** it documents at least 8 safety-compromise excuses with technical reality checks
- **AND** includes "NO FALLBACK POLICY" and "UNBOUNDED TTL ON LOCKS" as explicit refutations

#### Scenario: redis-application-patterns includes behavior errors table
- **WHEN** backend-redis-application-patterns SKILL.md is loaded
- **AND** it contains a "Rationalization Table - Redis Behavior Errors" section
- **THEN** it documents at least 8 Redis-specific excuses with correct pattern guidance
- **AND** includes "NO FALLBACK POLICY" and "REPOSITORY LEAKAGE" as explicit errors

#### Scenario: redis-infra-separation includes separation violations table
- **WHEN** backend-redis-infra-separation SKILL.md is loaded
- **AND** it contains a "Rationalization Table - Separation Violations" section
- **THEN** it documents at least 8 separation-violation excuses with architecture consequences
- **AND** includes "INFRA IN APP SKILL" and "PROVISIONING EMBEDDED" as explicit violations

#### Scenario: node-init-minimal includes bootstrap errors table
- **WHEN** backend-node-init-minimal SKILL.md is loaded
- **AND** it contains a "Rationalization Table - Bootstrap Errors" section
- **THEN** it documents at least 8 bootstrap-overreach excuses with scope boundaries
- **AND** includes "BUSINESS ROUTES" and "INFRASTRUCTURE SETUP" as explicit exclusions

---

### Requirement: RED-GREEN-REFACTOR sections for testing structure
All six backend skills SHALL include RED-GREEN-REFACTOR sections defining baseline testing, skill implementation, and loophole-closing phases.

#### Scenario: backend-defensive-engineering includes RED-GREEN-REFACTOR workflow
- **WHEN** backend-defensive-engineering SKILL.md is loaded
- **AND** it contains "RED-GREEN-REFACTOR for Backend Workflows" section
- **THEN** it defines three phases: Detection, Routing, and Invariant Preservation
- **AND** each phase has explicit Trigger, Agent Action, and Verification steps
- **AND** includes flowchart using Graphviz/dot syntax for delegation flow

#### Scenario: backend-core-architecture-contracts includes architecture testing phases
- **WHEN** backend-core-architecture-contracts SKILL.md is loaded
- **AND** it contains "RED-GREEN-REFACTOR for Architecture Contracts" section
- **THEN** it defines RED: Structural Analysis, GREEN: Contract Definition, REFACTOR: Invariant Documentation
- **AND** includes flowchart showing architecture boundary validation

#### Scenario: backend-runtime-safety-lifecycle includes safety verification phases
- **WHEN** backend-runtime-safety-lifecycle SKILL.md is loaded
- **AND** it contains "RED-GREEN-REFACTOR for Runtime Safety" section
- **THEN** it defines RED: Lifecycle Contract, GREEN: Health Implementation, REFACTOR: Cleanup Verification
- **AND** includes flowchart for dependency criticality classification

#### Scenario: redis-application-patterns includes pattern validation phases
- **WHEN** backend-redis-application-patterns SKILL.md is loaded
- **AND** it contains "RED-GREEN-REFACTOR for Redis Patterns" section
- **THEN** it defines RED: Policy Definition, GREEN: Consistency Implementation, REFACTOR: Lock Safety
- **AND** includes cache consistency flowchart with decision diamonds

#### Scenario: redis-infra-separation includes separation enforcement phases
- **WHEN** backend-redis-infra-separation SKILL.md is loaded
- **AND** it contains "RED-GREEN-REFACTOR for Separation Enforcement" section
- **THEN** it defines RED: Concern Classification, GREEN: Skill Routing, REFACTOR: Handoff Validation
- **AND** includes flowchart showing application vs infrastructure routing logic

---

### Requirement: Common Mistakes and Red Flags with STOP protocols
All six backend skills SHALL include Common Mistakes sections with explicit STOP conditions that halt work immediately when detected.

#### Scenario: backend-defensive-engineering defines red flags for immediate halt
- **WHEN** backend-defensive-engineering SKILL.md is loaded
- **AND** it contains "Red Flags - STOP and Start Over" section
- **THEN** it lists at least 8 red flag violations requiring immediate stop
- **AND** each flag includes specific STOP protocol: announce, halt, return to safe state
- **AND** includes "CODE BEFORE PROPOSAL" and "MIXED CONCERNS" as explicit triggers

#### Scenario: backend-core-architecture-contracts defines architecture violations
- **WHEN** backend-core-architecture-contracts SKILL.md is loaded
- **AND** it contains "Red Flags - Architecture Violations" section
- **THEN** it lists at least 8 architecture violations requiring halt
- **AND** includes "CONTROLLER LOGIC", "MISSING DTO", and "NO ERROR TAXONOMY" as explicit violations
- **AND** provides yellow flags (warnings) for review requiring verification

#### Scenario: backend-runtime-safety-lifecycle defines safety violations
- **WHEN** backend-runtime-safety-lifecycle SKILL.md is loaded
- **AND** it contains "Red Flags - Safety Violations" section
- **THEN** it lists at least 8 safety violations requiring immediate halt
- **AND** includes "NO GRACEFUL SHUTDOWN", "MISSING HEALTH ENDPOINTS", "LIVENESS DOES DEEP CHECKS"
- **AND** provides STOP protocol announcement and escalation trigger words

#### Scenario: redis-application-patterns defines Redis anti-patterns
- **WHEN** backend-redis-application-patterns SKILL.md is loaded
- **AND** it contains "Red Flags - Redis Behavior Anti-Patterns" section
- **THEN** it lists at least 8 Redis-specific anti-patterns requiring halt
- **AND** includes "NO FALLBACK POLICY", "UNBOUNDED TTL ON LOCKS", "UNCONDITIONAL LOCK RELEASE"
- **AND** includes lock-specific violations (TTL > 60 seconds)

#### Scenario: redis-infra-separation defines separation failures
- **WHEN** backend-redis-infra-separation SKILL.md is loaded
- **AND** it contains "Red Flags - Separation Violations" section
- **THEN** it lists at least 6 critical separation failures
- **AND** includes "INFRA IN APP SKILL", "PROVISIONING EMBEDDED", "NO HANDOFF DOCUMENTATION"
- **AND** provides escalation trigger words: "provision", "deploy", "cluster", "failover", "backup"

#### Scenario: node-init-minimal defines bootstrap overreach
- **WHEN** backend-node-init-minimal SKILL.md is loaded
- **AND** it contains "Red Flags - Bootstrap Overreach" section
- **THEN** it lists at least 7 overreach violations requiring halt
- **AND** includes "BUSINESS ROUTES", "AUTH INTEGRATION", "INFRASTRUCTURE SETUP"
- **AND** provides compatibility rule violations checklist

---

### Requirement: Cross-referencing with REQUIRED BACKGROUND sections
All six backend skills SHALL include explicit REQUIRED BACKGROUND sections with prerequisite skill names and cross-reference requirements.

#### Scenario: backend-defensive-engineering references orchestrator dependencies
- **WHEN** backend-defensive-engineering SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: openspec-proposal, backend-core-architecture-contracts, backend-runtime-safety-lifecycle
- **AND** includes guidance: "Do not proceed with routing until prerequisite skills are loaded"
- **AND** provides explicit unambiguous cross-references to companion skills

#### Scenario: backend-core-architecture-contracts references architecture dependencies
- **WHEN** backend-core-architecture-contracts SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: backend-defensive-engineering, openspec-proposal, backend-runtime-safety-lifecycle
- **AND** includes related skills: backend-redis-application-patterns, backend-auth-session-hardening

#### Scenario: backend-runtime-safety-lifecycle references lifecycle dependencies
- **WHEN** backend-runtime-safety-lifecycle SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: backend-defensive-engineering, openspec-proposal, backend-core-architecture-contracts
- **AND** includes downstream dependencies: affects backend-redis-application-patterns readiness checks

#### Scenario: redis-application-patterns references Redis prerequisites
- **WHEN** backend-redis-application-patterns SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: backend-defensive-engineering, openspec-proposal, backend-core-architecture-contracts, backend-runtime-safety-lifecycle
- **AND** includes alert: "backend-redis-infra-separation MUST be loaded to avoid infra/app conflation"
- **AND** includes warning: "Violating this separation violates the defensive engineering contract"

#### Scenario: redis-infra-separation references separation prerequisites
- **WHEN** backend-redis-infra-separation SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: backend-defensive-engineering, backend-redis-application-patterns
- **AND** includes alert: "Violating this separation violates the defensive engineering contract"

#### Scenario: node-init-minimal references bootstrap prerequisites  
- **WHEN** backend-node-init-minimal SKILL.md is loaded
- **AND** it contains "REQUIRED BACKGROUND" section
- **THEN** it lists: backend-defensive-engineering, backend-core-architecture-contracts, backend-runtime-safety-lifecycle
- **AND** provides guidance for existing projects vs greenfield bootstrap

---

### Requirement: Token optimization meets targets
All six backend skills SHALL meet token efficiency targets after defensive enhancement.

#### Scenario: backend-defensive-engineering targets 450-550 words
- **WHEN** backend-defensive-engineering SKILL.md word count is measured
- **THEN** it falls between 450-550 words (currently 382 + 70-170 added)
- **AND** includes optimization strategy: topology moved to separate file

#### Scenario: backend-core-architecture-contracts targets 400-450 words
- **WHEN** backend-core-architecture-contracts SKILL.md word count is measured
- **THEN** it falls between 400-450 words (currently 336 + 64-114 added)
- **AND** includes optimization: convert pitfalls to table format

#### Scenario: backend-runtime-safety-lifecycle targets 300-350 words
- **WHEN** backend-runtime-safety-lifecycle SKILL.md word count is measured
- **THEN** it falls between 300-350 words (currently 226 + 74-124 added)
- **AND** includes optimization: tables instead of bullet lists

#### Scenario: redis-application-patterns targets 280-320 words
- **WHEN** backend-redis-application-patterns SKILL.md word count is measured
- **THEN** it falls between 280-320 words (currently 197 + 83-123 added)
- **AND** includes optimization: detailed implementation in separate files

#### Scenario: redis-infra-separation targets 200-250 words
- **WHEN** backend-redis-infra-separation SKILL.md word count is measured
- **THEN** it falls between 200-250 words (currently 140 + 60-110 added)
- **AND** includes optimization: standalone format, keep concise

#### Scenario: node-init-minimal targets 180-220 words
- **WHEN** backend-node-init-minimal SKILL.md word count is measured  
- **THEN** it falls between 180-220 words (currently 168 + 12-52 added)
- **AND** includes optimization: add red flags, keep minimal otherwise

---

### Requirement: Flowcharts use Graphviz/dot format 
All backend skills with non-obvious decision points SHALL include flowcharts using Graphviz/dot syntax.

#### Scenario: backend-defensive-engineering includes delegation flowchart
- **WHEN** backend-defensive-engineering SKILL.md is loaded
- **AND** it contains "Deterministic Precedence Flowchart" section
- **THEN** the flowchart uses valid Graphviz/dot syntax with decision diamonds and boxes
- **AND** uses semantic labels (not "step1", "helper2")

#### Scenario: backend-core-architecture-contracts includes boundary flowchart
- **WHEN** backend-core-architecture-contracts SKILL.md is loaded
- **AND** it contains architecture boundary validation flowchart
- **THEN** it includes decision nodes for "Controller Contains Business Logic?" and "Service Returns Raw DB Rows?"
- **AND** provides clear routing to resolution steps

#### Scenario: backend-runtime-safety-lifecycle includes dependency classification flowchart
- **WHEN** backend-runtime-safety-lifecycle SKILL.md is loaded
- **AND** it contains dependency criticality classification flowchart
- **THEN** it distinguishes "Fail-Fast Critical?" vs "Optional Degrade-and-Warn?"
- **AND** provides visual routing to strict vs lenient policy configuration

#### Scenario: redis-application-patterns includes consistency flowchart
- **WHEN** backend-redis-application-patterns SKILL.md is loaded
- **AND** it contains cache consistency flowchart
- **THEN** it includes decision for "Write-Through?" vs "Cache-Aside?"
- **AND** provides routing to appropriate implementation patterns

#### Scenario: redis-infra-separation includes routing flowchart
- **WHEN** backend-redis-infra-separation SKILL.md is loaded
- **AND** it contains separation decision flowchart
- **THEN** it includes checks for "Application Behavior?" vs "Infrastructure?" vs "Both?"
- **AND** provides clear routing: application → app skill, infrastructure → infra path, both → split

---

### Requirement: Metadata updated with explicit dependencies
All six backend skills SHALL have their frontmatter metadata updated to include explicit cross-references in YAML requires field.

#### Scenario: backend-defensive-engineering metadata lists all companions
- **WHEN** backend-defensive-engineering SKILL.md frontmatter is parsed
- **THEN** requires field contains array: [openspec-proposal, backend-core-architecture-contracts, backend-runtime-safety-lifecycle, backend-redis-application-patterns, backend-redis-infra-separation, backend-node-init-minimal]

#### Scenario: backend-core-architecture-contracts metadata updated
- **WHEN** backend-core-architecture-contracts SKILL.md frontmatter is parsed
- **THEN** requires field contains array with: [backend-defensive-engineering, openspec-proposal, backend-runtime-safety-lifecycle]

#### Scenario: backend-runtime-safety-lifecycle metadata updated
- **WHEN** backend-runtime-safety-lifecycle SKILL.md frontmatter is parsed
- **THEN** requires field contains array with: [backend-defensive-engineering, openspec-proposal, backend-core-architecture-contracts]

#### Scenario: redis-application-patterns metadata includes separation dependency
- **WHEN** backend-redis-application-patterns SKILL.md frontmatter is parsed
- **THEN** requires field contains array with: [backend-defensive-engineering, openspec-proposal, backend-core-architecture-contracts, backend-runtime-safety-lifecycle, backend-redis-infra-separation]

#### Scenario: redis-infra-separation metadata references application skill  
- **WHEN** backend-redis-infra-separation SKILL.md frontmatter is parsed
- **THEN** requires field contains array with: [backend-defensive-engineering, backend-redis-application-patterns]

#### Scenario: node-init-minimal metadata lists prerequisites
- **WHEN** backend-node-init-minimal SKILL.md frontmatter is parsed
- **THEN** requires field contains array with: [backend-defensive-engineering, backend-core-architecture-contracts, backend-runtime-safety-lifecycle]

---