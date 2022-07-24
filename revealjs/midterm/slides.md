<!-- .slide: data-background-color="#8D3AED" -->

# Cryptography, Economics and Blockchains Midterm

## Analysing a Blockchain Whitepaper

<widget-text style="padding: 0 3em 0 3em">

---

##  Introduction

<widget-text style="padding: 0 3em 0 3em">

Who are the members of your team?


Aaryamann, Adam, Anton, Daan, Frank & Mattia

---


What blockchain or blockchain project are you analyzing?


We analyzed the Cardano blockchain project. [Whitepaper](https://whitepaper.io/document/581/cardano-whitepaper)

---

What are the core offerings of this blockchain/project?

Cardano's core offerings are as follows:

- Formal verification/strong proofs a core feature of Cardano (formal methods to achieve strong guarantees)
- Delegated Proof-of-Stake as a consensus mechanism

---

- Decentralised funding mechanism
- Separation of concerns: separation of settlement (value transfer) and computation layers (smart contracts)
- Regulation

---

What does it allow users to do?

- Fast and cheap transactions
- Low barrier of entry to block production
- Decentralised governance
- Decentralised storage

---

What is the differentiator for this project?

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

## Main Primitives

---

### Asymmetric Encryption
Asymmetric keys are used by nodes and addresses

---

### Certificates

- Operational certificates

- Delegation certificates

---

### Hashes

The hashing algorithm for all verification keys and multi-signature scripts is BLAKE2b-224 (64 bit). Explicitly, 
this is the payment and stake credentials, the genesis keys and their delegates, stake pool verification keys, and 
VRF verification keys.

---

## Exotic Primitives

Most of the exotic primitives are used in the governance spec.

---

### Additive Homomorphic Encryption

Post-Voting stage in governance: enables generation of the seed for the next round, which can be decrypted by _t_ of _n_ committee
members. 

---

### Non-Interactive Zero Knowledge (NIZK's)

Voting and Post-Voting stage in governance: the world's first honest ZK verifier, which is used to tally votes.

---

### Pederson Commitments

Voting stage in governance: used to anonymize votes for a proposal.

---

### Sealed Glass Proofs

Sealed Glass Proofs are proposed in the Cardano Computation Layer, which are a form of zero knowledge proof in a secure enclave.

---

### Verifiable Random Functions

- Used by Ouroboros Praos, the consensus mechanism for private slot leader selection. Leader selection was public in 
  previous versions of the protocol, so anyone could determine which node had the right to produce a block.

- Used in combination with NIZK's, Pederson Committments and Additive Homomorphic encryption to provide a random seed for the next voting round in governance.

---

## Digital Signatures

---

The chain currently only supports EdDSA and Curve25519 for signing and verification (with added support for HD 
wallets), but ECDSA SECP256k1 and Schnorr Ed25519 are due imminently for improved interoperability

---

Other signature schemes can be added through soft-forks

---

## Hash-based data structures

---

### Plutus Merkle Trees

The Hydra protocol(under active development), which create state channels for eUTXO's, use on-chain Merkle Trees for storage.

---

## Two things we liked

1. Usage of additive homomorphic encryption to encrypt the random seed for voting. This enables the seed to be decrypted with only a threshold of signers.
2. Usage of NIZKs to hide the vote from each voter

---

## Two things we disliked

1. The dependence on Sealed Glass Proofs to power the CCL increases the barrier of entry for regular validators who don't have machines with secure enclaves.
2. Computational overhead due to the use of so many exotic cryptographic primitives.

---

<!-- .slide: data-background-color="#8D3AED" -->

# 2. Economics

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the use of tokenomics in this project; name at least two things you like and two things you would want to improve.

* Does this project involve a native coin or currency? What are the tokenomics of the coin? How is the coin earned?
* How does this project use economic incentives to drive behavior?
* Use at least 3 of the following economic concepts in your answer:
    * Market Equilibrium (Supply and Demand): What is the supply schedule of the token, does it have inflation or deflation? Who will want to use the coin, and for what?
    * Economic Specialization
    * Game Theoretical Models
    * Auction Mechanics and Price Discovery Methods

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

* #### Staking
* Fees
* Governance

---

### Staking

--- 

- Stake pools - run by the stake pool operator (SPO)
* public and private stake pools
* 

- Pledging "skin in the game" - For each epoch, the SPO has to submit a pledge
		   - The higher the pledge, the higher the pool the reward



---

## Token utility

* Staking
* #### Fees
* Governance

---

### Fees
---

## Token utility

* Staking
* Fees
* #### Governance

---


Stake pools:
- Maximum size for stake pools
- Validators run a stake pool and ask commission from the delegators. Delegators delegate their stake to a staking pool and get rewarded proportionally to their stake. There is a latency period of 15-20 days, but delegators can unstake their stake whenever they want.
- “Parameter K”: defines how many pools there should be in the network and an estimated cap for their respective stake. Any amount of stake that surpasses this stake won’t earn additional reward.
- No slashing
- The Cardano environment is unique in the way it handles fees, as fees do not go directly to the block producer. Instead, they are pooled and then distributed to all pools that created blocks during an epoch.

|Market equilibrium|: see tokenomics and stake pools

|Economic specialization|: governance, keeping the network alive and potentially more with the possibility to write smart contracts on the csl/ccl?

|Game theoretical models|: (just wrote some stuff down which we could use, not entirely sure for me what they want to see here)
equilibrium
public good game
tragedy of commons


|Auction mechanics|: side chains, will look into this now (Daan)


|price discovery methods|:
Fees are constructed around two constants (a and b). The formula for calculating minimal fees for a transaction (tx) is: 
a * size(tx) + b		
where:
- a reflects the dependence of the transaction cost on the size of the transaction. The larger the transaction, the more resources are needed to store and process it.
- b is a payable fee, regardless of the size of the transaction. This parameter was primarily introduced to prevent Distributed-Denial-of-Service (DDoS) attacks. b makes such attacks expensive, and eliminates the possibility of an attacker generating millions of small transactions to flood and crash the system.
* size(tx) is the transaction size in bytes
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

---

<!-- .slide: data-background-color="#8D3AED" -->

# 6. Threat Models and Security

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the security protocols of this project; name at least two things you like and two things you would want to improve.

* How does this project protect against threats?
    * Byzantine Generals Problem
    * 51% Attack
    * Sybil Attack
    * Other Attacks

* How does this project provide secure transactions?

---

<!-- .slide: data-background-color="#8D3AED" -->

# 7. Conclusion

---

<widget-text style="padding: 0 3em 0 3em">

Summarize your findings by connecting the most important ideas together and answering these questions:

1. How do the cryptographic elements, the economic incentives and the blockchain parameters all contribute to the core goals of this blockchain?

2. Of the things that you identified you liked the _most_, what were the two top things you would highlight?

3. Of the things that you identified you liked the _least_, what were the two top things you would highlight?

4. Describe a way you would devise an attack on this system.

---

## Extra Credit/Stretch Goal

<widget-text style="padding: 0 3em 0 3em">

* Implement the attack described in the conclusion

* Propose an improvement to one or two aspects of your critique and implement it

---
