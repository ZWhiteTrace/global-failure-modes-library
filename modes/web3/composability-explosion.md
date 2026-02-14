# Composability Explosion

Protocol A is safe. Protocol B is safe. A + B together explodes.

## Warning Signs

- [ ] Protocol assumes it controls all entry points
- [ ] External calls to unknown contracts without reentrancy guards
- [ ] Token callbacks (ERC-777, ERC-1155) not considered
- [ ] View functions return mid-transaction inconsistent state
- [ ] "We only integrate with audited protocols" as security argument

## Real-World Examples

**Curve + Multiple Protocols (2023)**: Read-only reentrancy in Curve's `get_virtual_price()` allowed attackers to exploit lending protocols that used it as oracle during callback.

**Yearn + Cream (2021)**: Flash loan through one protocol manipulated state that another protocol trusted.

**Fei + Rari (2022)**: Reentrancy in one protocol exploited cross-contract state dependency. $80M lost.

## The Fundamental Problem

```
Protocol A: Audited ✓ Safe in isolation ✓
Protocol B: Audited ✓ Safe in isolation ✓
Protocol A reading Protocol B during A's external call: 💥

A's audit didn't know B exists
B's audit didn't know A would read mid-transaction
```

## Why It Persists

- Audits are scoped to single protocol
- "Composability" is a feature, not a risk
- Cross-protocol attack vectors require attacker thinking
- Teams celebrate integrations without modeling risks
- DeFi culture rewards "money legos" without safety analysis

## Incentive Structure

**Short-term beneficiaries:**
- Protocol teams (TVL goes up with integrations)
- Users (yield farming across protocols)
- Marketing ("compatible with 50+ protocols!")

**Long-term risk bearers:**
- Users across entire integration graph
- Protocols whose reputation gets blamed
- Insurance/coverage providers

## Mitigation Checklist

1. **Reentrancy guards on ALL state-mutating functions**: Not just the obvious ones

2. **Read-only reentrancy protection**: Lock flag checked even in view functions

3. **Don't trust external protocol state mid-transaction**:
   - Use TWAP or cached values
   - Never read live state during callback

4. **Explicit integration risk analysis**: For each integration, ask:
   - What can they call back into us?
   - What state do they read from us?
   - What if their state is manipulated?

5. **Pull over push**: Let users withdraw rather than pushing funds

6. **Assume every external call is hostile**: Even to "trusted" protocols

## One-Line Takeaway

In DeFi, security is not additive — your protocol is only as safe as its weakest integration.

## Related Modes

- [Flash Loan Arbitrage Blindness](./flash-loan-arbitrage-blindness.md)
- [Responsibility Laundering](../responsibility-laundering.md)
