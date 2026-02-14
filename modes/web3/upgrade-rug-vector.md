# Upgrade Rug Vector

Proxy upgradeability = trust assumption. "Immutable" smart contracts that can be changed anytime.

## Warning Signs

- [ ] UUPS/Transparent proxy with EOA admin (not multisig)
- [ ] No time-lock on upgrades
- [ ] Upgrade authority not documented or obscured
- [ ] "The code is audited" but upgrade key is single point of failure
- [ ] Implementation can be changed to anything with no on-chain constraints

## Real-World Examples

**Multichain (2023)**: $126M+ frozen/stolen. Admin keys compromised, upgraded contracts to drain funds.

**Wormhole-adjacent risks**: Bridge contracts with upgrade keys are constant targets. One compromised key = all funds.

**Nomad Bridge (2022)**: While not strictly an upgrade attack, showed how one parameter change (via upgrade-like mechanism) opened $190M exploit.

## The Fundamental Problem

```
User sees: "Audited smart contract" ✓
Reality: Contract can be upgraded to anything by admin
Actual trust assumption: Admin key security (often unknown)

"Trustless" DeFi that requires trusting a 3/5 multisig
where you don't know the signers
```

## Why It Persists

- Upgradeability is necessary for bug fixes (real reason)
- Teams want to retain control (hidden reason)
- Users don't check proxy admin before depositing
- "Decentralized" protocols with centralized upgrade keys
- Legal ambiguity: upgradeable = plausible deniability

## Incentive Structure

**Short-term beneficiaries:**
- Teams (can fix bugs, add features)
- Users (bugs get patched)

**Long-term risk bearers:**
- Users (admin key = god mode)
- Protocol (key compromise = total loss)
- Ecosystem (trust erosion)

## Mitigation Checklist

### For Protocol Teams:

1. **Multisig admin**: Never EOA, minimum 3/5 or 4/7

2. **Time-lock on upgrades**: 24-48 hours minimum
   - Users can exit before malicious upgrade executes

3. **Transparent upgrade process**:
   - Announce upgrades publicly before execution
   - Publish new implementation code before time-lock ends

4. **Upgrade constraints**:
   - On-chain limits on what can change
   - Storage layout verification

5. **Immutability roadmap**: Plan to remove upgrade keys eventually

### For Users:

1. **Check proxy admin before depositing**:
   ```
   cast admin <proxy_address>
   ```

2. **Verify multisig threshold**: Is it really 3/5 or is it 1/1?

3. **Check time-lock**: Is there delay before upgrades execute?

4. **Monitor upgrade events**: Set alerts for `Upgraded` events

## Trust Hierarchy

```
Most Trustless:
  └─ Immutable contract (no upgrade path)
     └─ Time-locked DAO governance (7+ days)
        └─ Time-locked multisig (24-48 hours)
           └─ Multisig without time-lock
              └─ EOA admin ← Maximum trust assumption
```

## One-Line Takeaway

Every upgradeable contract is one compromised key away from total loss.

## Related Modes

- [Governance Capture](./governance-capture.md)
- [Responsibility Laundering](../responsibility-laundering.md)
