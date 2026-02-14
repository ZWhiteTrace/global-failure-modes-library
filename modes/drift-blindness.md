# Drift Blindness

Gradual deviation from baseline goes unnoticed because each small change seems acceptable.

## Warning Signs

- [ ] "It's always been like this" (but it hasn't)
- [ ] No historical baselines to compare against
- [ ] Slow performance degradation accepted as normal
- [ ] Configuration drift across environments

## Real-World Examples

**Knight Capital (2012)**: A dormant trading algorithm was accidentally reactivated. Over 45 minutes, the system's behavior drifted catastrophically from normal patterns. No alerts triggered because each trade was within individual thresholds. Lost $440 million. Company bankrupt within days.

**Boeing 737 MAX (2018-2019)**: MCAS system gradually expanded in scope during development. Original safety analysis became outdated but wasn't revisited. Pilots weren't told the system existed. 346 deaths in two crashes.

**Infrastructure**: Servers gradually accumulating state drift from golden image.

**Security**: Password policies relaxed incrementally over years.

## Mitigation Checklist

1. **Baseline Documentation**: Record initial state explicitly
2. **Periodic Comparison**: Regular audits against baseline
3. **Trend Monitoring**: Alert on gradual changes, not just thresholds
4. **Fresh Eyes Review**: New team members question "why is it like this?"
5. **Immutable Infrastructure**: Rebuild rather than patch

## Operations Questions

- Do we have documented baselines for critical systems?
- How would we detect a 1% daily degradation?
- When did we last compare current state to original design?

## Related Modes

- [Normalization of Deviance](./normalization-of-deviance.md)
- [Goodhart's Trap](./goodharts-trap.md)
