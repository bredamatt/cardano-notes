<!-- .slide: data-background-color="#8D3AED" -->

# 5. Blockchain Structure

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the blockchain structure of this project; name at least two things you like and two things you would want to improve.

## Things we like about the structure
## Things we would improve
~~The documentation is frustratingly hard to navigate.
Having to parse formal verification papers and numerous white papers without any
assurance that the version of the paper you have matches to the current state of
the project is maddening.~~

## Core elements
* What are the core elements of the application stack?
### Cardano Settlement Layer (CSL)
### Cardano Computation Layer (CCL)

## Consensus algorithm
The consensus algorithm that is used is Ouroboros Praos[^2].

### Definitions
Beacon: Ouroboros uses a VRF ,called a beacon, to generate a random number.
The beacon regularly emits a new random value which is then used for
stakeholder elections.

Epoch: A point in protocol execution where the set of stakeholders eligible
to be block producers does not change. Each epoch has it's own beacon.

Slot: Every epoch is divided up equally to a number of slots.
This relation determines the block time such that if epoch is 1 hour
and the number of slots is 60, that would produce 1 block every minute.

Slot leader: the online stakeholder that is eligible to produce a new block.

Block: every slot should have a produced block which includes the current state,
other data, the slot number and a signature from the block creator.

### How it works

For every slot in the epoch, every online stakeholder will:

1. redetermine the stakeholder distribution if a new epoch has started
1. collect and verify all gossiped chains, compute the best chain via the `maxvalid` function, set that as the new local chain and update the state
1. if the online stakeholder is the slot leader, they will create a new block


## Block structure

The anatomy of a block is as follows[^1]:
```
{
    header: {
        prev    // hash of previous block header
        vk      // block issuer
        vrfVk   // VRF verification key
        blockno // block number
        slot    // block slot
        n       // nonce
        prf_n   // nonce proof
        l       // leader election value
        prf_l   // leader election proof
        bsize   // size of the block body
        bhash   // block body hash
        oc      // operational certificate
        pv      // protocol version
    },
    transactions: []
}
```

## State transition function
The state transition function (STF)[^3] is defined by the **chain** transition.

### Chain transition
Depends on:
- The **chain** transition is the base state transition in the STF and as such does not have any dependencies

Ensures that:

- The slot is incremented by one
- The block number is incremented one
- The prev hash matches the hash of the previous block header
- The size of the block header is smaller than the maximum block header size of the protocol
- The size of the block body is smaller than the maximum block body size of the protocol
At a later point, the block body size will be compared to the claimed size in the block header
- The protocol version field is not out of date, i.e. that the major version is larger than or equal to the MaxMajorPV constant.
- The **chain** transition calls the **block body**, **tick** & **protocol** sub-transitions

### Protocol transition
Depends on:
- The **block body**

Ensures that:
- The **overlay** sub-transition finishes
- The **update nonces** sub-transition finishes

#### Overlay transition
Ensures that:
- The **Ocert** sub-transition finishes

##### Ocert transition

#### Update nonces transition
Ensures that:
- the nonces get updated until the randomness gets fixed

### Tick transition
Depends on:
- The **block body**
- The **protocol**

Ensures that:
- The **reward update** sub-transition finishes
- The **new epoch** sub-transition finishes

#### Reward update transition
Ensures that:
- the current reward will be recalculated if the current slot algorithm allows it
- the current reward will not b recalculated if the current slot algorithm disallows it
- that if the current reward has already been calculated, the state will not update

#### New epoch transition
Depends on:
-  The **reward update**

Ensures that:
- The **move instantaneous rewards** sub-transition finishes
- The **complete epoch boundary** sub-transition finishes

##### Move instantaneous rewards (MIR) transition
Ensures that:
- if the reserve and treasury pots can cover the sum of pending instantaneous rewards, the accounts affected are paid the correct amount and the reserve and treasury drained. After, both of the instantaneous reward mappings are reset to the empty mapping

##### Complete epoch boundary transition
Depends on:
- The **move instantaneous rewards** transition
Ensures that:
- The **new protocol parameter** sub-transition finishes
- The **snapshot** sub-transition finishes
- The **pool reaping** sub-transition finishes

##### New protocol parameter transition
Ensures that:
- The new parameters will not incur a debt that cannot be covered by the reserves
- That the maximum block size is larger than the max transaction size and the max header size combined

##### Snapshot transition
A snapshot contains stake, delegation and pool parameter data.

Depends on:
- The **new protocol parameter** transition
Ensures that:
- The oldest snapshot is replaced by the middle snapshot
- The middle snapshot is replaced by the newest snapshot
- The newest snapshot is replaced by the just computed snapshot

##### Pool reaping transition
Responsible for removing pools that are to be retired in the current epoch.

Depends on:
- The **new protocol parameter** transition

Ensures that:
- Each retiring pool will refund it's deposit to the registered reward account if it still exists
- The sum total of refunds from retired pools with invalid reward accounts will go to the treasury
- The deposit pool is decremented by the sum total of claimed and unclaimed refunds
- All delegation certificates to the retiring pool are revoked
- The retiring pool is removed from all pool state mappings

### Block body transition
Ensures that:

- The block body size matches the value given in the block header
- The block body hash  matches the value given in the block header
- The **ledgers** sub-transition finishes

#### Ledgers transition
This is one of two recursive state transitions.

Depends on: 
- The **ledger** transition
Ensures that:
- The **ledger** sub-transition finishes

#### Ledger transition
Ensures that:
- The **unspent transaction output witness** sub-transition finishes
- The **delegators** sub-transition finishes

#### Unspent transaction output witness transition
Ensures that:
- The transaction has valid signatures or multisigs
- The transaction's verification keys are a subset of the needed verification keys
- The set of scripts given by the transaction is equal to the set of required scripts
- All instantaneous reward certificates have consensus
- The transaction metadata hash is equal to the hash of the transaction metadata or both properties are absent
- The **unspent transaction output** sub-transition finishes

##### Unspent transaction output transition
Ensures that:
- The transactions supplied get converted to outputs
- The sum total of all the coin for every output is calculated
- The *protocol parameter update*** sub-transition finishes

##### Protocol parameter update transition
Ensures that:
- If received *PP-Update-Empty*, do nothing
- If received *PP-Update-Current*, and it's still early in the epoch, add the parameters to the proposals with an override
- If received *PP-Update-Future*, add the parameters to the future proposals with an override. This proposal will then be dealt with in the next epoch

#### Delegations transition
This is one of two recursive state transitions.
Is used to handle stake delegation and pools.
Since pool certificates are disjoint from delegation certificates,
only one of the two rules will be successful.

Depends on:
- The **unspent transaction output witness** transition

Ensures that:
- The list of delegation/pool certificates is valid for every transaction that carries such a list

[^2]: Ouroboros Praos - https://eprint.iacr.org/2017/573.pdf

[^1]: Block specification - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#subsection.12.2

[^3]: Transition rule dependencies - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#section.14

---
