# Goodhart's Trap

"When a measure becomes a target, it ceases to be a good measure."

## Warning Signs

- [ ] Teams optimizing metrics at expense of actual goals
- [ ] Gaming behavior around KPIs
- [ ] Metrics improving while user experience degrades
- [ ] "Teaching to the test" patterns

## Real-World Examples

**Wells Fargo**: Employees opened fake accounts to hit account-opening targets.

**SEO**: Content optimized for search ranking, unreadable by humans.

**Code Coverage**: Tests written to hit coverage %, not to catch bugs.

## Mitigation Checklist

1. **Multiple Metrics**: Never rely on single metric
2. **Counter-Metrics**: Pair efficiency metrics with quality metrics
3. **Qualitative Checks**: Regular human review of outcomes
4. **Metric Rotation**: Periodically change what's measured
5. **Goal Reconnection**: Regularly ask "what are we actually trying to achieve?"

## System Design Questions

- Are we measuring what matters or what's easy to measure?
- What behaviors might this metric incentivize unintentionally?
- How would a bad actor game this metric?

## Related Modes

- [Drift Blindness](./drift-blindness.md)
