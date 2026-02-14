# failure-check

Analyze code, architecture, and systems against documented failure patterns.

## Trigger Conditions

Activate this skill when the context involves:
- Code review (especially with automation, AI, or financial logic)
- Architecture decision records (ADR)
- Smart contract review or audit
- DeFi protocol analysis
- System design with unclear ownership or accountability
- Post-incident analysis or RCA
- Metric-driven optimization systems

## Instructions

### Step 1: Context Detection

Identify the domain:
- **General software**: Check core failure modes
- **Web3/DeFi/Smart contracts**: Check BOTH core AND web3 failure modes
- **Organizational/Process**: Focus on responsibility and normalization patterns

### Step 2: Load Relevant Modes

Read the failure mode index:
- Core modes: `modes/INDEX.md`
- Web3 modes: `modes/web3/INDEX.md` (if blockchain/DeFi context)

### Step 3: Pattern Matching

For each failure mode, scan for warning signs in the code/design:

**Core Patterns:**
| Mode | Look For |
|------|----------|
| Automation Bias | Uncritical AI output usage, no human verification |
| Responsibility Laundering | "The algorithm decided", diffused ownership |
| Goodhart's Trap | Metric gaming, KPIs disconnected from purpose |
| Drift Blindness | Baseline erosion, "it's always been like this" |
| Normalization of Deviance | Known rule violations accepted |

**Web3 Patterns:**
| Mode | Look For |
|------|----------|
| Flash Loan Blindness | "Attack too expensive", no atomic manipulation checks |
| Oracle Trust Cascade | Single oracle, no staleness check, spot price usage |
| Composability Explosion | External calls without reentrancy guards, state reads mid-tx |
| Governance Capture | Token concentration, no time-lock, flash loan voting |
| Upgrade Rug Vector | EOA admin, no time-lock, unclear upgrade authority |

### Step 4: Output Format

```markdown
## Failure Mode Analysis

### [Mode Name]
**Risk**: LOW / MEDIUM / HIGH / CRITICAL
**Confidence**: LOW / MEDIUM / HIGH

**Warning Signs:**
- [ ] [Specific observation from code/design]
- [ ] [Another observation]

**Evidence:**
`file:line` - [code snippet or design element]

**Recommendation:**
1. [Actionable mitigation]
2. [Verification step]

**Reference:** [Link to mode documentation]
```

## Output Guidelines

- Only report modes with actual evidence (don't guess)
- Link specific code/design elements to warning signs
- Provide actionable recommendations, not just warnings
- If no patterns detected, explicitly state "No failure mode patterns detected"
- For Web3: Always check flash loan + oracle + reentrancy as baseline

## Quick Reference

### Core Failure Modes (5)
1. **Automation Bias** - Uncritical trust in automated systems
2. **Responsibility Laundering** - Accountability diffused through abstraction
3. **Goodhart's Trap** - Metrics gaming destroys original intent
4. **Drift Blindness** - Gradual deviation goes unnoticed
5. **Normalization of Deviance** - Rule violations become accepted

### Web3 Failure Modes (5)
1. **Flash Loan Arbitrage Blindness** - Assuming capital prevents attacks
2. **Oracle Trust Cascade** - Single oracle = single point of failure
3. **Composability Explosion** - Safe protocols unsafe when combined
4. **Governance Capture** - Token voting becomes plutocracy
5. **Upgrade Rug Vector** - Upgradeable = one key from total loss

## Example Invocation

User: "Review this smart contract for potential issues"

Claude should:
1. Detect Web3 context → load both core and web3 modes
2. Scan for: oracle usage, external calls, upgradeability, governance
3. Map findings to specific failure modes
4. Output structured analysis with evidence and recommendations
