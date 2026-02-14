# Governance Capture

Democratic facade, autocratic reality — when token voting becomes plutocracy.

## Warning Signs

- [ ] Top 10 wallets control >50% voting power
- [ ] DAO proposals pass with <5% participation
- [ ] "Governance minimized" used to avoid accountability
- [ ] Team/VCs retain veto power or majority tokens
- [ ] Flash loan governance attacks possible (vote + execute in same block)

## Real-World Examples

**Beanstalk (2022)**: Attacker flash-loaned governance tokens, passed malicious proposal, drained $182M — all in one transaction. No time-lock.

**Build Finance (2022)**: Hostile governance takeover. Attacker accumulated tokens, passed proposal to transfer treasury to themselves.

**Compound Governance (2020-ongoing)**: Whale-dominated voting. Key decisions made by <10 addresses. "Decentralized" in name only.

## The Fundamental Problem

```
Token-weighted voting assumes:
- Token distribution is fair ✗
- Voters are informed ✗
- Voters have aligned incentives ✗
- Attackers can't borrow voting power ✗
```

## Why It Persists

- "Decentralized governance" is good marketing
- Token voting is easy to implement
- Plutocracy benefits large holders (who build the systems)
- Alternative mechanisms (quadratic, conviction) are harder
- Legal grey area prefers appearance of decentralization

## Incentive Structure

**Short-term beneficiaries:**
- Large token holders (control without accountability)
- Teams (decentralization theater for regulators)
- VCs (exit liquidity with governance premium)

**Long-term risk bearers:**
- Small holders (diluted, outvoted)
- Users (decisions made against their interest)
- Protocol legitimacy (governance theater erodes trust)

## Mitigation Checklist

1. **Time-locks on proposals**: Minimum 2-7 days between proposal and execution

2. **Quorum requirements**: Meaningful participation threshold (not 1%)

3. **Flash loan protection**: Snapshot voting power at proposal creation, not execution

4. **Voting power caps**: Maximum influence per address/entity

5. **Rage quit mechanisms**: Allow minorities to exit before hostile proposal executes

6. **Multi-sig backstop**: Emergency pause capability for critical exploits

7. **Honest labeling**: If 5 people control it, don't call it "decentralized"

## Governance Security Checklist

```
□ Can someone flash loan governance tokens and pass a proposal?
□ What's the minimum time between proposal and execution?
□ Can proposal content be changed after voting starts?
□ Is there a guardian/emergency pause?
□ What percentage of tokens are required for quorum?
□ Who actually votes? (check on-chain participation)
```

## One-Line Takeaway

Token-weighted voting without safeguards is just plutocracy with extra steps.

## Related Modes

- [Responsibility Laundering](../responsibility-laundering.md)
- [Normalization of Deviance](../normalization-of-deviance.md)
