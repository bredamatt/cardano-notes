
<!-- .slide: data-background-color="#8D3AED" -->

# Economics

---

| Seed Sale                                           | Amount                   |
|-----------------------------------------------------|--------------------------|
| Public                                              | 25.9 billion ADA (57.6%) |
| [IOHK](https://iohk.io) (development company)       | 2.46 billion ADA (5.5%)  |
| [EMURGO](https://emurgo.io) (commercial adoption)   | 2.07 billion ADA (4.6%)  |
| [Cardano Foundation](https://cardanofoundation.org) | 640 million ADA (1.4%)   |
| Reserve / Uncirculated                              | 13.9 billion ADA (30.9%) |

---

### Inflation

The rate of inflation is 0.3% of the reserve per epoch (every 5 days), where:
- 80% will be used to reward staking pools
- 20% goes to the treasury

---

## Token utility

* Staking
* Fees
* Governance

---

#### Stake pools 
- Run by the stake pool operator (SPO)
- reliable operator: an individual or business with the knowledge and resources to run the 
node on a consistent basis
- Saturation parameter "k" - desired number of pools, indicating the max. amount of ADA per pool ideal for the network (64 million)
- Public and private stake pools, private when filled by the pledge

---

#### Pledging 
- "Skin in the game" - for each epoch, the stake pool owners have to submit a pledge
- Not meeting the pledge will result in no rewards
- The pledge increases the pool reward
- Attractive to delegators

---

#### Delegating
- Staking ADA by delegating to a stake pool
- High pledge and low margin effect the pool attractiveness
- Tokens are not locked

---

![](./midterm/cardano_payout.png)

---

#### Pool rewards
Stake pools are rewarded by the sum of:
- 80% of the monetary expansion.
- All the transaction fees during the new epoch.
- Fixed costs - a fixed fee of 340 ADA to every pool (covers the pool's operating costs).

---

![](./Description/img_2.png)

- Rewards increase with stake pool "size" until the pool is saturated
- the higher the pledge influence factor, the more important the size of the pledge

---

### Fees

The formula for calculating minimal fees for a transaction (tx) is:
#### a * size(tx) + b		

- A reflects the dependence of the transaction cost on the size of the transaction
- B is a payable fee
- size(tx) is the transaction size in bytes

---

### Takeaways
- Cardano has aligned its economic incentives to encourage decentralization. Rewards are shared between delegators and stake pool operators, a symbiotic relationship maximising rewards so long as they are intelligent and rational, and there is complete information.
- In addition, it incentivises a balanced distribution of stake across pools towards perfect competition, allowing delegators and stake pools to find market equilibrium.
- The design also allows for economic specialization: stake pool operators have the time, technical expertise and capital to run nodes which secure the network. Delegators may have none of these, instead delegating their stake to a stake pool to increase the overall pool stake, thereby increasing the probability of the stake pool
being elected to earn block rewards.

---

### Two things we liked
* Rewards shared between stake pool operators and delegators, no lock up period so delegators can easily re-stake with
  another operator if a stake pool performs poorly or its operator behaves maliciously (liquid democracy).
* No slashing, reducing delegator staking risk.

---

### Two things we disliked
* The pledge can be removed at any time
* No slashing
