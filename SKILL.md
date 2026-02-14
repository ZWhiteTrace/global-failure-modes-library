# failure-check

Skill for analyzing code and systems against known failure patterns.

## Usage

When reviewing code, architecture decisions, or system designs, invoke this skill to check against documented failure modes.

## Instructions

1. Read the failure mode index at `modes/INDEX.md`
2. For each relevant failure mode, check if the current context exhibits warning signs
3. Output findings in this format:

```
## Failure Mode Analysis

### [Mode Name] - Risk Level: LOW/MEDIUM/HIGH

**Warning Signs Detected:**
- [specific observation]

**Recommendation:**
- [actionable suggestion]
```

## Failure Modes Covered

- **Automation Bias**: Over-reliance on automated systems
- **Responsibility Laundering**: Diffused accountability through abstraction
- **Goodhart's Trap**: Metrics becoming targets, losing original intent
- **Drift Blindness**: Gradual deviation from baseline going unnoticed
- **Normalization of Deviance**: Repeated violations becoming accepted norm

## When to Invoke

- Code reviews involving automation or AI-assisted decisions
- Architecture discussions with unclear ownership
- Systems with heavy metric-driven optimization
- Long-running projects with accumulated technical debt
- Post-incident analysis
