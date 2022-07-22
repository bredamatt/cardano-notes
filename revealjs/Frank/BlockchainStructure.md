# Blockchain Structure

---

**Goal:** Evaluate the blockchain structure of this project; name at least two things you like and two things you would want to improve.

---
## State Transition Function
What is the state transition function of this blockchain/project?

## Application Stack
What are the core elements of the application stack?

## Block Anatomy
What is the anatomy of a block in this system?

## Consensus Algorithm

### Proof of Stake
"A fundamental problem for PoS-based blockchain protocols is to simulate the leader election process. In order to 
achieve a fair randomized election among stakeholders, entropy must be introduced, and mechanisms to introduce 
entropy may be prone to manipulation by the adversary"[^1].

The basic characteristics are therefore:
  * Based on local state, a participant is capable of deciding, in a **publicly verifiable** way, whether eligible 
    to produce next block[^2].
  * If adversary cannot predict eligibility of a stakeholder to issue a block prior to corrupting it, no advantage 
    can be gained by directing its corruption quota to specific stakeholders.
  * Assuming block valid, other participants update their local state by adopting block, and proceed in this way 
    continuously.
  * At any moment, probability of being permitted to issue a block is proportional to relative stake a player 
    has in the system (as reported by blockchain itself).
  * The probabilistic mechanism should be designed so that the adversary cannot bias it to its advantage.
  * As stake shifts over time, together with evolving population of stakeholders, so does honest majority assumption. 
    The function that appoints stakeholders should therefore continuously take ledger status into account.

### Ouroboros
The first "provably secure" proof-of-stake blockchain protocol, which had the ability to generate unbiased 
randomness in the slot leader selection algorithm. Randomness was added to the protocol via the `entropy parameter`, 
with the value being calculated by events not known in advance. 

Ouroboros selects a slot leader via randomly selecting stakeholders (weighted by stake) to form a committee in regular 
intervals called epochs. The committee forms a public leader schedule for the next epoch, which determines which stake 
pool is eligible to propose a block for which slot within the epoch. Slot leaders produce blocks along with a 
cryptographic proof, which is then verified by other network participants before being 
diffused to others to perform protocol synchronisation.

#### Byzantine Fault Tolerance
The second implementation enabled deterministic consensus through synchronous communication.

- "Slot leaders" which confirm transactions and create blocks (~20 secs)
- "Input endorsers" attest to blocks

#### Praos
The current implementation of the protocol provides an **adaptively-secure**, **semi-synchronous** proof-of-stake
blockchain. It secures against adaptive attackers using forward secure signatures in a semi-synchronous setting.

It also made the chain more modular, to allow better composition: e.g. network delegation, sidechains, checkpoints,  
different RNG, different sync assumptions and light client data structures.

Slot leader kept private so cannot be determined in advance, but once announced VRF key used to prove eligibility.

* Adaptive Corruption
* Partial/Semi-Synchronous Model
  * Time divided into slots, one block per slot. Participants roughly synchronised clocks that indicate current slot,
    allowing distributed protocol to assign blocks to slots. Current slot determined by publicly known and 
    monotonically increasing function of current time.
  * Protocol execution divided into slots, max delay of ∆ slots applied to message delivery (liveness)
  * Semi-synchronisation:
    * Time between slots should be long enough to allow network to sync
    * Slots can be empty, if no blocks received by deadline. Frequent empty slots (forks) occur to enable short 
      periods of silence that facilitate synchronisation
  * Probabilistic: following longest chain enables honest parties to converge to unique view with highest probability
* Private Leader Selection
  * Deciding whether participant eligible to propose block decided by verifiable random function (VRF) on current timestamp and nonce determined for epoch
  * VRF with unpredictability under malicious key generations: Provided high entropy, output of VRF must be *unpredictable*, even if key generation procedure has been subverted
* Forward Secure Signatures

* Guarantees
    * Adversary can corrupt any participant at any time, as long as stakeholder distribution maintains honest majority stake
    * Tolerates adversarially-controlled message delivery delay unknown to participants
    * Achieved through forward secure digital signatures and new type of verifiable random function

* Static Stake
  * Initial set of stakeholders/string of randomness, assumed to be honest (genesis block)
  * Randomness used to select stakeholders assigned to initial slots, weighted by stake
    * Weighted-by-stake sampling: stakeholder elected based on ??

* Bootstrapping:
  * Randomness beacon available to all participants: beacon emits randomness at regular intervals so participants can re-seed election process
    * "leaky resettable beacon": resilient to leaks to adversary ahead of time and and allows adversary to reset its value if it wishes (within a bounded time window)
  * "leaky resettable beacon" implemented as algorithm that concatenates VRF outputs from participants from blockchain, subjected to a hash function modeled as a random oracle
  * Approach makes "grinding attack" feasible, but controlled by increasing parameters based on hashing power available to adversary
* Transaction Ledger Properties
  * Robust provided ledger divided into blocks (assigned to time slots) that determines order transactions incorporated into ledger

* Semi-synchronous model

  * Security model
    * Delayed Diffuse: allows for adversarially-controlled delayed delivery of messages diffused among stakeholders
      * Keeps rounds, executing 1 round per slot
      * Maintains incoming message for each stakeholder. Activated stakeholders can fetch message into 'inbox' or request **diffuse** for message, once per round.
      * Activated adversary allowed to a) read all inboxes and all diffuse requests and deliver messages to inbox in any order it prefers, b) reclassify diffuse requests as **delayed**, c) move message from delayed to inbox
      * At end of each round, every message is either a) diffused in this round and not delayed, or b) removed from delayed in round and delivered to stakeholder inbox.
      * Any message currently delayed which was diffused at least ∆ slots ago is removed from delayed and moved to participant inbox
      * New stakeholder spawned with  existing chain as its initial chain
  * Modelling Protocol Execution and Adaptive Corruptions
    * Environment issues transactions on behalf of stakeholder by requesting signature on transaction and handling to stake holders to include in blocks
    * Adversary can only corrupt stakeholder if given permission by environment running protocol execution
    * Adversary immediately corrupts stakeholder without delay
    * Corrupted stakeholder will relinquish state to adversary: from this point on adversary activated in place of stakeholder
    * Adversary able to control transactions and blocks generated by corrupted parties
  * Restrictions imposed by environment
    * Adaptive corruption can grant adversary great power so important to restrict environment suitably
    * Require that in every slot adversary does not control 50% of stake in view of any honest stakeholder
    * When environment spawns new stakeholder, initial local chain can be chain of any honest stakeholder, without requiring stakeholder to have been online in past slot
  * Random Oracle
    * assume availability of random oracle, available to all parties that answers every fresh query with an independent uniformly random string
  * Erasures: assume honest users can do secure erasures
  * Static Stake Protocol
    * Similar to (synchronous) Ouroboros, but introduces modifications to leadership selection process
    * Not all slots attributed a a slot leader
      * Empty slots, where no block generated, allow honest parties to synchronise
    * Some slots might have multiple slot leaders
    * Slot leader identities remain unknown until they act
      * Used to deal with adaptive corruptness: prevents adversary from learning slot leaders identity ahead of time and using this knowledge to strategically corrupt coalitions of parties with large future influence
    * Definition 1 (Genesis Block)
      * Contains list of stakeholders identified by label, their respective public keys and respective stakes and a nonce
      * Nonce used to seed the slot leader election process
    * Definition 2 (State, Block, Proof, Block, Blockchain, Epoch)
      * State is a string
      * Block proof is a value (or set of values) containing information allowing stakeholders to verify block is valid
      * Block generated at slot contains current state, data, slot number, block proof, signature of stakeholder under signing key for time period of slot
      * Chain is a hash of resulting sequence of blocks (relative to genesis block) associated with increasing sequence of slots.
        * Length of chain is (non-negative) number of blocks
        * Empty string is a valid chain
      * Epoch is set of adjacent slots
      * Valid blocks generated by stakeholder in slot leader set of slot to which block attributed
    * Definition 3: Absolute & Relative Stake
      * Forward Secure Signatures (with Erasures)
        * Prevent adversary from generating signatures for messages issued in the past, or rather allows honest users to verify given signature generated at a point in time
        * Achieved by evolving signing key after each signature key generated and erasing previous key so that actual signing key used in past cannot be recovered but fresh signing key still linked to previous one
        * Key evolving signature schemes: allow signing keys to be evolved into fresh keys for a number of time periods
        * Adversary that corrupts signer to forge signatures limited to current and future signing keys, but not a previous signing key
        * Key evolving operation packed together with signing operation
        * Adversary can only set response to signature verification query (taking time period as input) only if no key update performed since time period and no entry exists in internal table for specific message, signature and time period specified in query
        * Functionality
          * Key Generation
            * Upon receiving KeyGen request from stakeholder, send generated key to adversary
            * Upon receiving VerificationKey request from adversary, send verification key to stakeholder, record the triple (sid, stakeholder, v) and set counter to 1
          * Sign and Update
            * Upon receiving signing request(j) from stakeholder, verify that triple is recorded for some sid and that counter <= j <= total number of signature updates. If not, ignore the request otherwise increment the counter with j and send signature to adversary
            * Upon receiving signature from adversary, verify that no entry is recorded. If it is, output error and halt, otherwise send signature to stakeholder and record entry
          * Signature verification
            * Upon receiving a verification request from some stakeholder:
              * If verification key matches (is the registered one or legitimately generated signature for m) the verification succeeds
              * If verification matches, signer is not corrupted and no registered entry, record the entry. This condition guarantees unforgeability: if verification matches registered one, signer is not corrupted and never signed the message so verification fails
              * If already an entry recorded, return previous result: This condition guarantees consistency - all verification requests with identical parameters result in same answer
              * If j < counter, record entry. If j = counter, send verification request to adversary. Upon receiving verification from adversary, record entry. This condition guarantees adversary only able to forge signatures under keys belonging to corrupted parties for current or future slots
      * UC-VRFs with Unpredictability Under Malicious Key Generation
        * Unpredictability under malicious key generation: distribution of VRF outputs cannot be guaranteed if 
          adversary allowed to generate its own key pair. Adversary that maliciously generates keys can easily and significantly skew output distribution
        * Given a key generation request from one of stakeholders, returns new verification key that is used to label a table
        * Oblivious Leader Selection

---
### Footnotes
[^1]: https://eprint.iacr.org/2016/889.pdf
[^1]: Grinding attack: adversarial parties use computational resources to bias the randomness in their own favor
[^2]: Proof of eligibility computed publicly or via secret key computation/public key verification.
[^?]: Ouroborous implementations: Classic (2017), BFT (2019), Praos (current), Genesis, Hydra, Crypsinous, Chronos, 
Omega
