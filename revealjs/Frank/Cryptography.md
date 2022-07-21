# Cryptography

---

**Goal:** Evaluate the use of cryptography in this project; name at least two things you liked and two things you would want to improve.

---

## Primitives
What are the main cryptographic primitives used in this blockchain project?

### Exotic Primitives
Does this project use any exotic primitives?  If so, which ones?

#### Verifiable Random Functions
* Block production
  * VRFs are used by the Ouroboros Praos consensus mechanism for private slot leader selection. Leader selection 
    was public in previous versions of the protocol, so anyone could determine which node had the right to produce a 
    block.
  * Using VRFs keeps the slot leader schedule private until a leader is selected. The slot leader can then prove to 
    everyone that they are using the VRF key and produce a block.
  * todo: add more technical info on benefits 

### Digital Signatures
How does this project use digital signatures for security?

The chain supports multiple digital signature types including:
* ECC Ed25519 
* BLISS-B for quantum resistance (in future?), 
* SECP256k1 for interoperability
* Forward Secure Signatures?

### Hashing
How does this project use hashing and hash-based data structures to ensure security?
