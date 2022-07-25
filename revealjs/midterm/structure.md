<!-- .slide: data-background-color="#8D3AED" -->
# Blockchain Structure

---

## State transition function
<widget-text style="padding: 0 3em 0 3em">

<img src="../Description/stf.png" width="40%"/>

---

## Core elements

* Settlement layer *CSL*
* Computation layer *CCL*

---

## Settlement layer

* Handles the accounting and ledger actions a blockchain will make throughout it's lifetime
* UTXO based
* Supports user issued assets (NFTs, custom tokens)
* Will support multiple types of signatures, including quantum resistant signatures

---

## Computation layer

* Inspired by Rootstock, a smart contract platform on Bitcoin
* Will enable specialized protocols that can help Cardano scale
* Will probably use sealed glass proofs in Hardware Security Modules (HSM)
* Maybe live when Hydra launches?

---

## Block anatomy

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

---

## Transaction

```
{
    inputs: [
        0,
        ...
        N
    ],
    outputs: [
        0,
        ...
        M
    ]
}
```
* input being a solution to a previous output
* output being a problem with tokens attached
---

## Consensus algorithm

* Ouroboros Praos proof of stake consensus
* Divides time into Epochs and epochs into slots
  - Epoch = 5 days
  - Slot = 1 second
  - 432,000 slots per epoch

---

## Consensus algorithm

* Praos provides private leader elections
  - VRF based randomness
  - prevents adversaries from learning who the leader is
