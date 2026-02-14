# Failure Modes Index

Quick reference for all documented failure patterns.

| Mode | Domain | Key Signal | Severity |
|------|--------|------------|----------|
| [Automation Bias](./automation-bias.md) | Human-AI | Uncritical acceptance of AI output | High |
| [Responsibility Laundering](./responsibility-laundering.md) | Organization | "The algorithm decided" | Critical |
| [Goodhart's Trap](./goodharts-trap.md) | Metrics | Metric gaming, losing purpose | Medium |
| [Drift Blindness](./drift-blindness.md) | Operations | Slow baseline erosion | High |
| [Normalization of Deviance](./normalization-of-deviance.md) | Culture | "We always do it this way" | Critical |

## Usage Pattern

```
1. Identify context (code review / architecture / incident)
2. Scan for warning signals in INDEX
3. Deep dive into relevant mode documentation
4. Apply mitigation checklist
```
