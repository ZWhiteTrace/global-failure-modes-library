# Global Failure Modes Library

A curated collection of systemic failure patterns across industries, designed for practical application in code reviews, architecture decisions, and incident analysis.

## Quick Start

### As Claude Code Skill

```bash
# Copy to your skills directory
cp -r global-failure-modes-library ~/.claude/skills/

# Invoke during code review
# Claude will automatically reference failure patterns
```

### Manual Reference

Browse `modes/` directory for failure pattern documentation.

## Failure Modes

| Mode | One-Line Summary |
|------|------------------|
| [Automation Bias](modes/automation-bias.md) | Uncritical trust in automated systems |
| [Responsibility Laundering](modes/responsibility-laundering.md) | Accountability diffused through abstraction |
| [Goodhart's Trap](modes/goodharts-trap.md) | Metrics gaming destroys original intent |
| [Drift Blindness](modes/drift-blindness.md) | Gradual deviation goes unnoticed |
| [Normalization of Deviance](modes/normalization-of-deviance.md) | Rule violations become accepted practice |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) - designed for non-engineers to contribute failure patterns from their domains.

## License

[CC BY 4.0](LICENSE) - Share and adapt with attribution.

## Why This Exists

Complex systems fail in predictable patterns. By documenting these patterns with concrete warning signs and mitigations, we can:

1. **Prevent**: Recognize warning signs before failure
2. **Analyze**: Apply frameworks to incident post-mortems
3. **Design**: Build systems that resist known failure modes
4. **Educate**: Share cross-industry knowledge

## Acknowledgments

Inspired by works on system failures, organizational accidents, and human factors research.
