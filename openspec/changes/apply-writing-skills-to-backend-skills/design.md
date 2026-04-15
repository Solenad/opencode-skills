## Context

Backend skills currently state architectural rules but lack defensive structures that prevent rationalization under pressure. Skills include:
- backend-defensive-engineering (382 words)
- backend-core-architecture-contracts (336 words)  
- backend-runtime-safety-lifecycle (226 words)
- backend-redis-application-patterns (197 words)
- backend-redis-infra-separation (140 words)
- backend-node-init-minimal (168 words)

Writing-skills demonstrates proven defensive patterns: rationalization tables, RED-GREEN-REFACTOR testing structure, explicit STOP conditions, and CSO optimization. These patterns successfully close loopholes that cause architectural degradation.

The improvement requires retrofitting existing skills without changing requirements - this is defensive documentation enhancement, not behavioral change.

## Goals / Non-Goals

**Goals:**
- Make rules defensible under pressure by anticipating objections
- Provide explicit STOP protocols that halt work on violations
- Create decision flowcharts for non-obvious routing/precedence
- Optimize token usage while adding defensive value
- Ensure cross-references prevent skill loading failures

**Non-Goals:**
- Change existing architectural requirements or rules
- Add net-new capabilities or features
- Expand skill scope beyond current boundaries
- Migrate skills to new locations
- Change skill naming conventions

## Decisions

### Decision: Retrofit defense, don't redesign
**Choice**: Add defensive structures around existing content vs. rewriting skills
**Rationale**: Existing requirements are correct. Writing-skills patterns enhance enforcement, fixing a meta-problem (rule adherence) rather than a functional problem.
**Alternatives considered**:
- Full rewrite: Unnecessary risk, existing requirements proven correct
- New "defensive" companion skills: Fragmentation, harder to discover
- Inline annotations: Less visible than dedicated sections

### Decision: Use rationalization tables over FAQ sections
**Choice**: Explicit tables pairing "excuse" with "reality" 
**Rationale**: FAQ is passive; rationalization table is active defense. Testing shows agents more likely to respect documented counterarguments.
**Alternatives considered**:
- FAQ style: Less confrontational but easier to ignore
- "Common mistakes": Focuses on outcome, not the rationalization that led there
- Detailed explanations: Too verbose, less scannable

### Decision: RED-GREEN-REFACTOR instead of "Testing" section
**Choice**: Structure testing methodology as RED-GREEN-REFACTOR phases
**Rationale**: Forces explicit baseline testing (RED) before writing protections. Consistent with existing TDD-first principle in codebase.
**Alternatives considered**:
- "Testing considerations" section: Weaker, less prescriptive
- Example-driven: Misses the baseline comparison
- Implicit assumption testing works: Proven false - skills need baseline verification

### Decision: Flowcharts only for non-obvious decisions
**Choice**: Use flowcharts for routing/precedence, not linear processes
**Rationale**: flowcharts add most value for decision points where agents historically choose wrong, per writing-skills conventions.
**Alternatives considered**:
- All complex logic: Too many flowcharts, dilutes impact
- None: Text only = less visual, harder to scan
- Sequence diagrams: Wrong tool for decision points

### Decision: Token target <200 for orchestrators, <500 for specialized
**Choice**: Optimize for frequent loading: orchestrator skills get tighter budgets
**Rationale**: backend-defensive-engineering loads for every backend task. Premium token usage = better context utilization.
**Alternatives considered**:
- Uniform <500: Wastes context on frequently-loaded orchestrator
- Aggressive <150: Too restrictive for complex guidance
- No targets: No discipline on word count growth

### Decision: REQUIRED BACKGROUND instead of implicit dependencies
**Choice**: Explicit "You MUST understand X before using this skill" sections
**Rationale**: Writing-skills testing showed implicit dependencies fail - agents don't load prereq skills.
**Alternatives considered**:
- Metadata alone: Not visible enough in conversation flow
- Inline comments: Easy to miss when scanning
- Cross-reference links: Force-loads burn context

## Risks / Trade-offs

**[Risk] → Mitigation**

- **Adding content increases token usage** → Target <200 orchestrators, <500 specialized. Move verbose content to referenced files.

- **Flowcharts require Graphviz/dot syntax knowledge** → Provide example blocks. Use existing writing-skills conventions.

- **Rationalization tables may seem confrontational** → Phrase as "Reality" not "You're wrong". Tested approach from writing-skills.

- **Pressure scenarios require subagent testing** → Already practiced in writing-skills skill creation. Same methodology applies.

- **Changes to stable skills could introduce documentation errors** → Changes are defensive additions only, no rule modifications. Easier to verify.

- **Cross-references may duplicate metadata** → Metadata for machine routing, REQUIRED BACKGROUND for human visibility. Both necessary.

## Migration Plan

**Deployment order by dependency topology:**

1. **Apply backend-redis-infra-separation** (leaf node, no prerequisites)  
2. **Apply backend-node-init-minimal** (leaf node, no prerequisites)  
3. **Apply backend-runtime-safety-lifecycle** (depends on node-init)  
4. **Apply backend-redis-application-patterns** (depends on lifecycle and separation)  
5. **Apply backend-core-architecture-contracts** (depends on lifecycle)  
6. **Apply backend-defensive-engineering** (orchestrator, depends on all others)

**Rollout approach:**
- Each skill updated independently
- No interdependent releases
- No code changes required
- Skills usable immediately after commit

**No migration required**: Existing behavior unchanged, defensive additions only.

## Open Questions

- Should we create aggregate defensive stats view across all backend skills post-enhancement?
- Do we need a backend-testing-skills companion for pressure scenario examples?
- Should rationalization tables across skills be cross-referenced when themes repeat?
- Flowchart rendering: Should we document how to render them for human review?