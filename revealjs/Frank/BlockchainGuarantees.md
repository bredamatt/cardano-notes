# Blockchain Guarantees

---

**How does this blockchain/project guarantee the following?**

---
## Liveness
That the blockchain is always adding more transactions and that service will not be interrupted.

Persistence: Once node proclaims transaction `tx` as stable, the remaining nodes, if queried, will either report 
`tx` in same position in ledger or will not report as stable any transaction in conflict to `tx`. Transaction 
declared stable if in a block that is more than *k* blocks deep in the ledger.

Liveness: If all honest nodes in system attempt to include a transaction then, after the passing of time
corresponding to *u* slots (called the *transaction confirmation time*), all nodes, if queried and responding honestly,
will report the transaction as stable. 

Persistence and liveness derived from three properties:
- Common prefix
- Honest chain growth
- Existential chain quality

## Fairness
No systemic discrimination that is against the rules of the protocol

## Censorship-resistance
No individual actor or coalition can prevent the access of another to the system.

## Safety
No conflicting information.
