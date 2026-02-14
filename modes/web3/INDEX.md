# Web3 Failure Modes Index

Systemic failure patterns specific to DeFi, smart contracts, and blockchain protocols.

These are not just code vulnerabilities — they are **economic, governance, and systemic design failures** that audits often miss.

## Quick Reference

| Mode | Domain | Key Signal | Severity |
|------|--------|------------|----------|
| [Flash Loan Arbitrage Blindness](./flash-loan-arbitrage-blindness.md) | DeFi/Economic | "Attack too expensive" | Critical |
| [Oracle Trust Cascade](./oracle-trust-cascade.md) | DeFi/Infrastructure | Single oracle dependency | Critical |
| [Composability Explosion](./composability-explosion.md) | DeFi/Integration | Cross-protocol calls | Critical |
| [Governance Capture](./governance-capture.md) | DAO/Governance | Token concentration | High |
| [Upgrade Rug Vector](./upgrade-rug-vector.md) | Smart Contracts | Proxy admin trust | Critical |

## How Web3 Failure Modes Differ

Traditional security focuses on:
- Code correctness
- Access control
- Input validation

Web3 failures often involve:
- **Economic attacks**: Profitable exploitation, not just bugs
- **Atomicity abuse**: Flash loans, MEV, single-transaction exploits
- **Composability risks**: Safe protocols becoming unsafe when combined
- **Governance theater**: Decentralization in name only
- **Trust assumption gaps**: Users don't know what they're trusting

## Before Deploying / Investing

Ask these questions:

1. **Can this be exploited with flash-loaned capital?**
2. **What happens when the oracle returns stale/wrong data?**
3. **Who can upgrade this contract and how fast?**
4. **What other protocols does this depend on?**
5. **Is governance actually decentralized or just labeled that way?**

## Relationship to Core Failure Modes

Web3 failure modes often combine with general patterns:

- Flash Loan Blindness + **Automation Bias** → "The simulation passed"
- Oracle Cascade + **Drift Blindness** → "Chainlink has always worked"
- Governance Capture + **Responsibility Laundering** → "The DAO decided"
- Composability + **Normalization of Deviance** → "Other protocols do this"

## Contributing

If you've seen a Web3 failure pattern not covered here:
1. Use the [failure mode template](../../templates/failure-mode-template.md)
2. Focus on the **systemic pattern**, not just the specific incident
3. Include real examples with approximate dates and losses
