# Automation Bias

Over-reliance on automated systems, leading to uncritical acceptance of their outputs.

## Warning Signs

- [ ] AI/automated suggestions accepted without verification
- [ ] Manual checks skipped "because the system handles it"
- [ ] Alerts dismissed as false positives without investigation
- [ ] Human expertise atrophied due to automation dependency

## Real-World Examples

**Therac-25 (1985-1987)**: Radiation therapy machine killed 6 patients due to software bugs. Operators trusted the computer's safety interlocks completely. When the machine displayed errors, they assumed false positives and continued treatment. The manufacturer dismissed early reports because "the computer wouldn't allow unsafe doses."

**Air France 447 (2009)**: Pilots failed to recognize stall warnings because autopilot had always handled it. When sensors failed and autopilot disconnected, crew couldn't process raw flight data. 228 deaths.

**Healthcare**: Doctors accepting diagnostic AI recommendations without clinical judgment.

**Software**: Developers merging AI-generated code without understanding it.

## Mitigation Checklist

1. **Verify Before Trust**: Always spot-check automated outputs
2. **Maintain Skills**: Regular practice of manual procedures
3. **Question Defaults**: "Why did the system suggest this?"
4. **Document Overrides**: Track when humans override automation and why

## Code Review Questions

- Is there a human verification step for critical automated decisions?
- Can operators understand and explain automated outputs?
- Are there fallback procedures when automation fails?

## Related Modes

- [Responsibility Laundering](./responsibility-laundering.md)
