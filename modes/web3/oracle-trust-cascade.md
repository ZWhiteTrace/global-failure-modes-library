# Oracle Trust Cascade

Entire protocol chains depending on single oracle source — one stale price collapses everything.

## Warning Signs

- [ ] Multiple protocols read same Chainlink feed without independent validation
- [ ] No staleness checks (`updatedAt`, `answeredInRound`)
- [ ] L2 deployment without sequencer uptime verification
- [ ] "Chainlink is decentralized" used to skip redundancy
- [ ] Price deviation between sources dismissed as "temporary"

## Real-World Examples

**LUNA/UST (2022)**: Oracle reported stale prices during death spiral. Protocols using these prices allowed arbitrage that accelerated collapse.

**Mango Markets (2022)**: $114M exploit by manipulating low-liquidity oracle price. Attacker self-traded to move price, then borrowed against inflated collateral.

**L2 Sequencer Downtime**: Multiple incidents where Arbitrum/Optimism sequencer went down, oracles froze, liquidations happened at wrong prices.

## Why It Persists

- Oracle integration is "solved problem" — teams copy-paste without thinking
- Chainlink brand trust substitutes for actual redundancy design
- Multi-oracle systems are expensive to build and maintain
- Edge cases (stale, negative, zero prices) rarely hit in testing

## Incentive Structure

**Short-term beneficiaries:**
- Protocol teams (faster shipping)
- Auditors (oracle integration is "standard")

**Long-term risk bearers:**
- Users during oracle failure
- Protocols in cascade (one failure triggers many)
- Entire DeFi ecosystem (systemic risk)

## Mitigation Checklist

1. **Always check staleness**:
   ```
   require(block.timestamp - updatedAt < HEARTBEAT)
   require(answeredInRound >= roundId)
   ```

2. **L2: Check sequencer uptime feed** before trusting any price

3. **Multi-oracle with deviation bounds**: If TWAP vs Chainlink > 5%, pause or use fallback

4. **Handle edge cases explicitly**: Zero price, negative price, round not complete

5. **Circuit breakers**: Pause protocol if price moves > X% in Y time

6. **Assume oracle WILL fail**: Design for graceful degradation, not just "it works"

## One-Line Takeaway

Every oracle will eventually return wrong data — design for that moment.

## Related Modes

- [Flash Loan Arbitrage Blindness](./flash-loan-arbitrage-blindness.md)
- [Drift Blindness](../drift-blindness.md)
