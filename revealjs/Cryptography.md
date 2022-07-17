**Goal:** Evaluate the use of cryptography in this project; name at least two things you liked and two things you would want to improve.

## What are the main cryptographic primitives used in this blockchain project?

* For signatures and verification Cardano uses Ed25519 with added support for HD wallets. Other signatures maybe added through soft forks (in particular BLISS-B for anti-quantum and SECP256k1 for legacy)

* The hashing algorithm for all verification keys and multi-signature scripts is BLAKE2b-224. Explicitly, this is the payment and stake credentials, the genesis keys and their delegates, stake pool verification keys, and VRF verification keys.
Everywhere else we use BLAKE2b-256.

*

## Does this project use any exotic primitives?  If so, which ones?


* The verifyVrf function from uses ECVRF-ED25519-SHA512-Elligator2* I havent found anything on exotic primitives (additive homomorphic in voting? - yes)

* [Exotic primitives used in governance](#Cryptographic-aspects-of-governance)

## How does this project use digital signatures for security?
* It 



* It hashes verification keys, multi sigs and ... 
## How does this project use hashing and hash-based data structures to ensure security?



---


## Cryptographic aspects of governance

Following are the primitives used in governance - 


#### Commonly used primitives

- Digital signatures
  - [Pre-Voting] Signing keys are freshly generated to vote for each proposal 

- One way hash functions
  - [Pre-Voting] To generate the voter ID, and expert ID, which are hashes of the signing key generated for each proposal

- Public-key cryptography
  - [All-stages] Are used to sign transactions that are broadcasted onto the network
  
- Commitment scheme
  - [Pre-Voting] The seed which is used to select a random group of committee members to tally and execute votes is committed in the previous voting round, and revealed at the start of the new voting round

<!-- 
Potential Attack Vector or Deadlock Scenario:
Scenario:
  - The committee members commit the seed onchain
  - Majority go offline before the next pre-voting epoch
  - The seed for the next round of voting is not decrypted
  - The voting halts, and no new proposals can be created
-->


#### Exotic primitives

- Additive homomorphic encryption
  - [Post-Voting] Enables generation of the seed for the next round, which can be decrypted by t of n committee members. An implementation can be found [here](https://github.com/aistcrypt/Lifted-ElGamal)

- [Voting] Pederson Commitments
  - Are used to anonymize votes for a proposal

- [Voting and Post-Voting] NIZK's (Non Interactive Zero Knowledge)
  - The world's first honest ZK verifier, which is used to tally votes

