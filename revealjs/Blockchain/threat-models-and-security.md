# Threat Models and Security

## Two things we liked about the security of Cardano

- TODO maybe the upgradability to new hashing and signing primitives (futureproofing)? 

- TODO nizk for voting or maybe the additive homomorphic encryption for the seed generation?

## Two things we disliked about the security of Cardano

- TODO The committee seems like a vulnerability

- TODO 

## How does Cardano protect against common threats?

### Byzantine Generals Problem

Proof of Stake empowers the uncoordinated "Generals" to agree, based on the consensus mechanism, Ouroborous. Since there is a preset algorithm deciding which "General" is the leader, all the other "Generals" accept them as the leader, and by extension, accept the block that the leader creates, which can be verified to be valid.

### 51% Attack

No blockchain (consensus protocol rather?) can prevent a 51% attack (oof). Also, a BGP hijack (routing layer) can easily enable that - no protection mentioned.

### Sybil Attack

Ideally, the stake pool operator who controls a large amount of stake pools could control the entire network.

Sybil attacks are prevented in Cardano, by having the concept of "Pledging" of ADA by Stake Pool operators. By pledging a portion of their own funds, stake pool operators are entitled to having a bonus reward. By having a lower pledge, the stake pool operator obtains a smaller reward. This incentivizes stake pool operators to have a higher pledge, thereby, discouraging them from creating multiple stake pools.

## How does Cardano provide secure transactions?

TODO: not sure what they mean by this question (hashing?)
