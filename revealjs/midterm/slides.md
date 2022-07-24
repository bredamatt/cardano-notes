<!-- .slide: data-background-color="#8D3AED" -->

# Cryptography, Economics and Blockchains Midterm

## Analysing a Blockchain Whitepaper

<widget-text style="padding: 0 3em 0 3em">

---

##  Introduction

<widget-text style="padding: 0 3em 0 3em">

1. We are Aaryamann, Adam, Anton, Daan, Frank & Mattia

2. We analyzed the Cardano blockchain project. [Whitepaper](https://whitepaper.io/document/581/cardano-whitepaper)

3. What are the core offerings of this blockchain/project?

4. What does it allow users to do?

5. What is the differentiator for this project (what makes it unique from other blockchains or projects)?

    - Formal Verification
    - Seperation of the settlement layer and the computation layer
    - Support for legacy systems
    - *Private* liquid democracy

---

## Outline

<widget-text style="padding: 0 3em 0 3em">

1. Cryptography
1. Economics
1. Governance
1. Blockchain Structure
1. Blockchain Guarantees
1. Threat Models
1. Conclusion

---

<!-- .slide: data-background-color="#8D3AED" -->

# 1. Cryptography

---

**Goal:** Evaluate the use of cryptography in this project; name at least two things you liked and two things you would want to improve.

* What are the main cryptographic primitives used in this blockchain project?
* Does this project use any exotic primitives?  If so, which ones?
* How does this project use digital signatures for security?
* How does this project use hashing and hash-based data structures to ensure security?

---

<!-- .slide: data-background-color="#8D3AED" -->

# 2. Economics

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
- Cardano's incentive mechanisms seeks a balanced distribution of stake across pools towards perfect competition, allowing
- Stake pool operators have the time, technical expertise and capital to run nodes which secure the network. Delegators may have none of these, instead delegating their stake to a stake pool to increase the overall pool stake, thereby increasing the probability of the stake pool
being elected to earn block rewards.

---

### Pros:
* Rewards shared between stake pool operators and delegators, no lock up period so delegators can easily re-stake with
  another operator if a stake pool performs poorly or its operator behaves maliciously (liquid democracy).
* No slashing, reducing delegator staking risk.

---

### Cons:
* The pledge can be removed at any time
* No slashing

---


<!-- .slide: data-background-color="#8D3AED" -->

# 3. Governance

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the use of governance in this project; name at least two things you like and two things you would want to improve.

* How does this project solve the collective decision making problem?
* What are the structures of governance in this project? How are changes proposed and voted on?
* What voting mechanisms are used in this project?
* Who is allowed to vote in this project? What are the voting criteria?



---

<!-- .slide: data-background-color="#8D3AED" -->

# 4. Blockchain Guarantees

---

<widget-text style="padding: 0 3em 0 3em">

**How does this blockchain/project guarantee the following?**

* **Liveness:** That the blockchain is always adding more transactions and that service will not be interrupted.
* **Fairness:** No systemic discrimination that is against the rules of the protocol
* **Censorship-resistance:** No individual actor or coalition can prevent the access of another to the system.
* **Safety:** No conflicting information.

---

<!-- .slide: data-background-color="#8D3AED" -->

# 5. Blockchain Structure

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the blockchain structure of this project; name at least two things you like and two things you would want to improve.

* What is the state transition function of this blockchain/project?
* What are the core elements of the application stack?
* What is the anatomy of a block in this system?
* What is the consensus algorithm that is used? How does it work?
