# Flash Loan Arbitrage Blindness

Assuming "one transaction = limited capital" while flash loans make attack cost nearly zero.

## Warning Signs

- [ ] Protocol logic assumes attacker capital is bounded
- [ ] Price calculations use single-block spot prices
- [ ] "Too expensive to attack" used as security argument
- [ ] No consideration of atomic multi-step transactions

## Real-World Examples

**bZx (2020)**: Attacker flash-borrowed $10M, manipulated oracle price, borrowed against inflated collateral, repaid flash loan — all in one transaction. Cost: gas fees only.

**Cream Finance (2021)**: $130M drained using flash loans to manipulate price oracles and exploit lending logic.

**Euler Finance (2023)**: $197M exploit using flash loans to manipulate donation mechanism and liquidation logic.

## Why It Persists

- Traditional finance intuition: "attacks require capital"
- Flash loans are invisible until exploited
- Auditors focus on code correctness, not economic attacks
- "It worked on testnet" — testnets don't have flash loan liquidity

## Incentive Structure

**Short-term beneficiaries:**
- Protocol teams (ship faster without economic modeling)
- Auditors (code-only scope is cheaper)

**Long-term risk bearers:**
- Users (lose funds)
- Protocol reputation (unrecoverable)

## Mitigation Checklist

1. **Never use spot prices**: AMM reserves, single-block prices are trivially manipulable
2. **TWAP with long windows**: 30+ minutes for medium liquidity pools
3. **Multi-oracle validation**: Chainlink + TWAP deviation checks
4. **Delayed execution**: Time-lock critical operations across blocks
5. **Economic invariant testing**: Fuzz with unlimited attacker capital assumption

## One-Line Takeaway

In DeFi, assume every attacker has infinite capital for one block.

## Related Modes

- [Oracle Trust Cascade](./oracle-trust-cascade.md)
- [Composability Explosion](./composability-explosion.md)
