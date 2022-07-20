<!-- .slide: data-background-color="#8D3AED" -->

# 4. Blockchain Guarantees

---

<widget-text style="padding: 0 3em 0 3em">

**How does this blockchain/project guarantee the following?**

Taken wholly from the Ouroboros: A Provably Secure Proof-of-Stake Blockchain Protocol

* **Liveness:** That the blockchain is always adding more transactions and that service will not be interrupted.

Liveness and persistence are prioritised and based on $$u$$ and $$k$$ parameters respectively. It is shown that they can only be violated with very low probabilities.

Liveness: If all honest nodes in the system attempt to include a certain transaction, then after the passing of time corresponding to $$u$$ slots (called the transaction confirmation time), all nodes, if queried and responding honestly, will report the transaction as stable.

* **Fairness:** No systemic discrimination that is against the rules of the protocol

In order to achieve a fair randomized election among stake-holders, entropy must be introduced into the system. They utilize a (simple) secure multiparty implementation of a coin-flipping protocol to produce the randomness for the leader election process (anit-grinding). 

The protocol assumes that parties can freely create accounts and receive and make payments, and that stake shifts over time.

* **Censorship-resistance:** No individual actor or coalition can prevent the access of another to the system.

You can perform block withholding and/or endorsed input censorship to remove endorsed inputs from the blockchain that originate to honest parties. Then include the removed transactions in an endorsed input that will be transmitted in the last possible opportunity.

A possible direction for ameliorating this problem is to share the transaction fee of a transaction between all the input endorsers that endorsed it. This suggests the following modification to the protocol: whenever you are an input endorser you should attempt to include all transactions that you have collected for a sequence of $$k$$ slots and retransmit your endorsed input in case it is removed from the main chain.

* **Safety:** No conflicting information.

Not sure here.
---