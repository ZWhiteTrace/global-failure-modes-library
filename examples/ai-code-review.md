# Example: AI-Assisted Code Review

Applying failure modes analysis to AI-generated code review.

## Scenario

Developer uses AI to generate a smart contract for token staking.

## Failure Mode Check

### Automation Bias - Risk: HIGH

**Warning Signs Detected:**
- AI-generated Solidity code merged without manual security review
- "Claude/GPT wrote it, should be fine"

**Recommendation:**
- Manual audit of all external calls and state changes
- Cross-reference with known vulnerability patterns (reentrancy, overflow)
- Test edge cases AI might not have considered

### Responsibility Laundering - Risk: MEDIUM

**Warning Signs Detected:**
- If exploit occurs, who is accountable? "The AI wrote that part"

**Recommendation:**
- Document that human developer reviewed and approved each function
- Clear ownership in code comments: `// Reviewed by: @developer, 2025-01-15`

### Goodhart's Trap - Risk: LOW

**Warning Signs Detected:**
- Optimizing for "code coverage %" rather than actual security

**Recommendation:**
- Add invariant tests, not just line coverage
- Manual review of test quality, not just quantity

## Outcome

This analysis prevented deployment of a contract with an unreviewed external call pattern that could have enabled reentrancy.
