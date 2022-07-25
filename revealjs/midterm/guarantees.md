<!-- .slide: data-background-color="#8D3AED" -->


# Blockchain Guarantees

---

### Liveness

- If all honest nodes in the system attempt to include a transaction, then after $u$ slots (the transaction confirmation time) all nodes will report the transaction as stable.
- Since block production is probabilistic, delays can happen and large number of nodes as well as good synchronisation is required

* No guarantees for liveness of governance

---

### Fairness

- Achieved by randomising the choosing of stake-holders (coin-flipping protocol)

- Parties can freely create accountsand make transactions 

- Stake shifts over time

---

### Censorship-resistance

- Censorship of endorsed inputs can be performed by witholding blocks

- This can be avoided by sharing the transaction fee between all endorsers and should be implemented soon

---

### Safety

- Important for liveness

- Depends on the degree of decentralisation and number of validators

- Stake pools ensure safety

