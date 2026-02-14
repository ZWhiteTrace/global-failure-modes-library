# Responsibility Laundering

Diffusing accountability through layers of abstraction until no one is responsible.

## Warning Signs

- [ ] "The algorithm/model decided" used as justification
- [ ] Decision chains so long no single point owns outcomes
- [ ] Vendors blamed for system behavior
- [ ] "I just implemented what was specified"

## Real-World Examples

**Finance**: Algorithmic trading losses with no accountable party.

**Social Media**: Content moderation decisions attributed to "the algorithm."

**Autonomous Vehicles**: Unclear liability between manufacturer, software, operator.

## Mitigation Checklist

1. **Name the Owner**: Every automated decision needs a human accountable
2. **Decision Audit Trail**: Log who approved what at each layer
3. **Override Authority**: Clear chain for human intervention
4. **Outcome Ownership**: Someone must own the result, not just the process

## Architecture Questions

- Who is accountable when this system makes a wrong decision?
- Can we trace any automated action back to a human approval?
- Is there clear escalation path for edge cases?

## Related Modes

- [Automation Bias](./automation-bias.md)
- [Normalization of Deviance](./normalization-of-deviance.md)
