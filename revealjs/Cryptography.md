**Goal:** Evaluate the use of cryptography in this project; name at least two things you liked and two things you would want to improve.

## What are the main cryptographic primitives used in this blockchain project?

* For signatures and verification Cardano uses Ed25519 with added support for HD wallets. Other signatures maybe added through soft forks (in particular BLISS-B for anti-quantum and SECP256k1 for legacy)

* The hashing algorithm for all verification keys and multi-signature scripts is BLAKE2b-224 (64 bit). Explicitly, this is the payment and stake credentials, the genesis keys and their delegates, stake pool verification keys, and VRF verification keys.
Everywhere else we use BLAKE2b-256 (also 64bit).


*

## Does this project use any exotic primitives?  If so, which ones?


* The verifyVrf function from uses ECVRF-ED25519-SHA512-Elligator2* I havent found anything on exotic primitives (additive homomorphic in voting? - yes)

* [Exotic primitives used in governance](#Cryptographic-aspects-of-governance)

## How does this project use digital signatures for security?
* Key evolving signatures (KES) according to the MMM scheme. These type of signature schemes provide forward cryptographic security, meaning that a compromised key does not make it easier for an adversary to forge a signature that allegedly had been signed in the past. In KES, the public verification key stays constant, but the corresponding private key evolves
incrementally. For this reason, KES signing keys are indexed by integers representing the step in
the key’s evolution. This evolution step parameter is also an additional parameter needed for
the signing (denoted by sign ev ) and verification (denoted by verify ev ) functions.
Since the private key evolves incrementally in a KES scheme, the ledger rules require the pool
operators to evolve their keys every time a certain number of slots have passed, as determined
by the global constant SlotsPerKESPeriod.

* Multi sigs. The terms form a tree like structure and are evaluated via the evalMultiSigScript function. The parameters are a script and a set of key hashes. The function returns True when the supplied key hashes are a valid combination for the script, otherwise it returns False



* It hashes verification keys, multi sigs and ... for authentication of transaction data
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



#### Exotic primitives

- Additive homomorphic encryption
  - [Post-Voting] Enables generation of the seed for the next round, which can be decrypted by t of n committee members. An implementation can be found [here](https://github.com/aistcrypt/Lifted-ElGamal)

- [Voting] Pederson Commitments
  - Are used to anonymize votes for a proposal

- [Voting and Post-Voting] NIZK's (Non Interactive Zero Knowledge)
  - The world's first honest ZK verifier, which is used to tally votes

