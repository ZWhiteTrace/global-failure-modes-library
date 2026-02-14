# Failure Modes Index

Quick reference for all documented failure patterns.

## Core Failure Modes

| Mode | Domain | Key Signal | Severity |
|------|--------|------------|----------|
| [Automation Bias](./automation-bias.md) | Human-AI | Uncritical acceptance of AI output | High |
| [Responsibility Laundering](./responsibility-laundering.md) | Organization | "The algorithm decided" | Critical |
| [Goodhart's Trap](./goodharts-trap.md) | Metrics | Metric gaming, losing purpose | Medium |
| [Drift Blindness](./drift-blindness.md) | Operations | Slow baseline erosion | High |
| [Normalization of Deviance](./normalization-of-deviance.md) | Culture | "We always do it this way" | Critical |

## Web3 / DeFi Failure Modes

| Mode | Domain | Key Signal | Severity |
|------|--------|------------|----------|
| [Flash Loan Arbitrage Blindness](./web3/flash-loan-arbitrage-blindness.md) | DeFi | "Attack too expensive" | Critical |
| [Oracle Trust Cascade](./web3/oracle-trust-cascade.md) | DeFi | Single oracle dependency | Critical |
| [Composability Explosion](./web3/composability-explosion.md) | DeFi | Cross-protocol calls | Critical |
| [Governance Capture](./web3/governance-capture.md) | DAO | Token concentration | High |
| [Upgrade Rug Vector](./web3/upgrade-rug-vector.md) | Smart Contracts | Proxy admin trust | Critical |

See [Web3 Failure Modes Index](./web3/INDEX.md) for detailed documentation.

## Usage Pattern

```
1. Identify context (code review / architecture / incident)
2. Scan for warning signals in INDEX
3. Deep dive into relevant mode documentation
4. Apply mitigation checklist
```
