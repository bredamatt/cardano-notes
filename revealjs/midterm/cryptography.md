<!-- .slide: data-background-color="#8D3AED" -->

# Cryptography

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

### Pedersen Commitments

Voting stage in governance: used to anonymize votes for a proposal.

---

### Sealed Glass Proofs

Sealed Glass Proofs are proposed in the Cardano Computation Layer, which are a form of zero knowledge proof in a secure enclave.

---

### Verifiable Random Functions

- Used by Ouroboros Praos, the consensus mechanism for private slot leader selection. Leader selection was public in 
  previous versions of the protocol, so anyone could determine which node had the right to produce a block.

- Used in combination with NIZK's, Pedersen Committments and Additive Homomorphic encryption to provide a random seed for the next voting round in governance.

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

