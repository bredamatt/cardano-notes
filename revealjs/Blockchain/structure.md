<!-- .slide: data-background-color="#8D3AED" -->

# 5. Blockchain Structure

---

<widget-text style="padding: 0 3em 0 3em">

**Goal:** Evaluate the blockchain structure of this project; name at least two things you like and two things you would want to improve.

* What is the state transition function of this blockchain/project?
The STF [^3] [^4] is split into a a block transition and a chain transition.
The block transition ensures that:
    - The block body size matches the value given in the block header
    - The block body hash  matches the value given in the block header
    - The LEDGERS transition succeeds
The chain transition ensures that: 
    - The slot is incremented by one
    - The block number is incremented one
    - The prev hash matches the hash of the previous block header
    - The size of the block header is smaller than the maximum block header size of the protocol
    - The size of the block body is smaller than the maximum block body size of the protocol.
    At a later point, the block body size will be compared to the claimed size in the block header.
    - The protocol version field is not out of date, i.e. that the major version is larger than or equal to the MaxMajorPV constant.


* What are the core elements of the application stack?
* What is the anatomy of a block in this system?
The anatomy of a block[^1]:
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

* What is the consensus algorithm that is used? How does it work?
The consensus algorithm that is used is Ouroboros Praos[^2]

[^2]: Ouroboros Praos - https://eprint.iacr.org/2017/573.pdf
[^1]: Block specification - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#subsection.12.2
[^3]: Chain transition - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#subsection.12.14
[^4]: Block transition - https://hydra.iohk.io/build/4975913/download/1/ledger-spec.pdf#subsection.12.13

---