## Why

Backend skills currently state architectural rules but lack defensive structures that make them effective under pressure. They anticipate neither objections to the rules nor the rationalizations developers use to bypass them. Writing-skills demonstrates proven patterns (rationalization tables, RED-GREEN-REFACTOR testing structure, explicit STOP conditions) that close these loopholes and enforce discipline consistently.

This change applies those battle-tested defensive documentation patterns retroactively to backend skills, making them bulletproof against the "too simple to test", "too urgent to follow process", and "temporary deviation" excuses that cause architectural degradation.

## What Changes

- Add **Rationalization Tables** to all backend skills documenting common objections and their refutations
- Implement **RED-GREEN-REFACTOR testing structure** with subagent pressure scenarios
- Add **Common Mistakes + Red Flags sections** with explicit STOP protocols that halt work
- Update metadata with **explicit cross-references** using REQUIRED BACKGROUND markers
- **Token optimization**: Target <200 words for frequently-loaded skills, <500 for others
- **Flowcharts for decision points**: Visualize non-obvious delegation and precedence rules

## Capabilities

### New Capabilities
- None - this is a defensive enhancement to existing capabilities

### Modified Capabilities
The following existing skills will have defensive enhancements (requirements remain the same, implementation guidance becomes bulletproof):

- `backend-defensive-engineering`: Add rationalization tables, RED-GREEN-REFACTOR, red flags, flowcharts
- `backend-core-architecture-contracts`: Add anti-exception armor, architecture boundary flowchart, violations table
- `backend-runtime-safety-lifecycle`: Add safety compromise rationalizations, dependency classification flowchart
- `backend-redis-application-patterns`: Add behavior error rationalizations, consistency flowchart, lock safety verification
- `backend-redis-infra-separation`: Add separation violation excuses, handoff validation flowchart
- `backend-node-init-minimal`: Add bootstrap overreach red flags and STOP conditions

## Impact

**Affected Codebases**: All backend projects using these skills
**No breaking changes**: Existing rules unchanged; defensive structure added around them
**Dependencies**: None - this enhances existing patterns 
**Token impact**: +60-130 words per skill (acceptable for defensive value)