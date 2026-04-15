## 1. Baseline and planning

- [x] 1.1 Capture current baseline of all six backend skill files (word counts, section inventory, existing frontmatter fields)
- [x] 1.2 Create per-skill update plan mapping required sections: Rationalization Table, RED-GREEN-REFACTOR, Red Flags, REQUIRED BACKGROUND, Flowchart
- [x] 1.3 Define target word-count ranges per skill and identify content to move to supporting references if needed

## 2. Harden backend-defensive-engineering

- [x] 2.1 Add Rationalization Table with excuse→reality pairs for proposal skipping, mixed concerns, and undocumented deviations
- [x] 2.2 Add RED-GREEN-REFACTOR section with trigger/action/verification and delegation precedence flowchart
- [x] 2.3 Add Red Flags STOP protocol with explicit halt-and-reset behavior
- [x] 2.4 Add REQUIRED BACKGROUND section and update metadata requires field with explicit companion dependencies
- [x] 2.5 Verify skill remains within token target while preserving clarity

## 3. Harden backend-core-architecture-contracts

- [x] 3.1 Add Rationalization Table for controller logic leakage, raw datastore returns, and implicit invariants
- [x] 3.2 Add RED-GREEN-REFACTOR section for structure validation, DTO contract definition, and invariant verification
- [x] 3.3 Add architecture boundary flowchart for controller/service/repository decisions
- [x] 3.4 Add Red Flags section with immediate STOP conditions and corrective path
- [x] 3.5 Add REQUIRED BACKGROUND section and update metadata requires field

## 4. Harden runtime and Redis behavior skills

- [x] 4.1 Update backend-runtime-safety-lifecycle with Rationalization Table and RED-GREEN-REFACTOR lifecycle safety phases
- [x] 4.2 Add dependency criticality decision flowchart and safety red flags (shutdown, probes, readiness)
- [x] 4.3 Update backend-redis-application-patterns with Rationalization Table for fallback, lock TTL, ownership verification, and reconciliation
- [x] 4.4 Add RED-GREEN-REFACTOR Redis phases and cache consistency flowchart
- [x] 4.5 Add REQUIRED BACKGROUND sections and metadata dependency updates for both skills

## 5. Harden separation and bootstrap skills

- [x] 5.1 Update backend-redis-infra-separation with concern-classification Rationalization Table and separation decision flowchart
- [x] 5.2 Add Red Flags STOP protocol for infra/app conflation and missing handoff documentation
- [x] 5.3 Update backend-node-init-minimal with bootstrap-overreach Rationalization Table and STOP conditions
- [x] 5.4 Add REQUIRED BACKGROUND sections and metadata dependency updates for both skills

## 6. Verification and readiness

- [x] 6.1 Run pressure-scenario checks for each updated skill (baseline failure notes, post-update compliance checks)
- [x] 6.2 Verify all flowcharts use valid Graphviz/dot syntax and semantic labels
- [x] 6.3 Verify frontmatter consistency (name/description/tags/requires) across all modified skills
- [x] 6.4 Re-check word counts against targets and adjust for token efficiency where required
- [x] 6.5 Perform final review for scope fidelity (no requirement changes, defensive hardening only)
