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
## Block structure
* What is the anatomy of a block in this system?

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

## Chain transition
The state transition function (STF)[^3] is defined by the **chain** transition.

Depends on:
- The **chain** transition is the base state transition in the STF and as such does not have any dependencies.

Ensures that:

- The slot is incremented by one
- The block number is incremented one
- The prev hash matches the hash of the previous block header
- The size of the block header is smaller than the maximum block header size of the protocol
- The size of the block body is smaller than the maximum block body size of the protocol.
At a later point, the block body size will be compared to the claimed size in the block header.
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
Depends on:
- Nothing

Ensures that:
- the current reward will be recalculated if the current slot algorithm allows it.
- the current reward will not b recalculated if the current slot algorithm disallows it.
- that if the current reward has already been calculated, the state will not update.

#### New epoch transition
Depends on:
-  The **reward update**

Ensures that:
- The **move instantaneous rewards** sub-transition finishes
- The **complete epoch boundary** sub-transition finishes

##### Move instantaneous rewards (MIR) transition
Depends on:
- Nothing

Ensures that:
- if the reserve and treasury pots can cover the sum of pending instantaneous rewards, the accounts affected are paid the correct amount and the reserve and treasury drained. After, both of the instantaneous reward mappings are reset to the empty mapping.

##### Complete epoch boundary transition
Depends on:
- The **move instantaneous rewards** transition
Ensures that:
- The **new protocol parameter** sub-transition finishes
- The **snapshot** sub-transition finishes
- The **POOLREAP** sub-transition finishes

##### New protocol parameter transition
TODO

##### Snapshot transition
A snapshot contains stake, delegation and pool parameter data.

Depends on:
- The **new protocol parameter** transition
Ensures that:
- The oldest snapshot is replaced by the middle snapshot.
- The middle snapshot is replaced by the newest snapshot.
- The newest snapshot is replaced by the just computed snapshot.

##### POOLREAP transition
Depends on:
- The **new protocol parameter** transition
Ensures that:
TODO

### Block body transition
Depends on:
TODO
Ensures that:

- The block body size matches the value given in the block header
- The block body hash  matches the value given in the block header
- The LEDGERS transition succeeds

--

**Remaining questions:**

* What are the core elements of the application stack?

* What is the consensus algorithm that is used? How does it work?
The consensus algorithm that is used is Ouroboros Praos[^2]

[^2]: Ouroboros Praos - https://eprint.iacr.org/2017/573.pdf

[^1]: Block specification - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#subsection.12.2

[^3]: Transition rule dependencies - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#section.14

---
