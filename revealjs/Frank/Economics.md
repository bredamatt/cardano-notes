# Economics

---

## Tokenomics

### Native Token
The native token is ADA, named after Ada Lovelace, an English mathematician[^1], which is used for fees, rewards
and deposits.

Cardano does also have multi-asset support via "native tokens"[^2], but usage does not have any direct economic impact on
the network.

### Tokenomics:

#### Token Usage

* **Staking**: ADA stakers delegate to stake pools and earn rewards for securing the network
* **Fees**: transaction fees paid in ADA
* **Governance**: ADA stakers participate in governance and vote on CIPs

#### Distribution
There was a public sale of 25.9 billion ADA and an additional 5.2 billion ADA (20% of public) was allocated to the
three entities supporting the ongoing development of the project:

| Seed Sale                                           | Amount                   |
|-----------------------------------------------------|--------------------------|
| Public                                              | 25.9 billion ADA (57.6%) |
| [IOHK](https://iohk.io) (development company)       | 2.46 billion ADA (5.5%)  |
| [EMURGO](https://emurgo.io) (commercial adoption)   | 2.07 billion ADA (4.6%)  |
| [Cardano Foundation](https://cardanofoundation.org) | 640 million ADA (1.4%)   |
| Reserve / Uncirculated                              | 13.9 billion ADA (30.9%) |

#### Supply Schedule
Cardano currently has approximately 75% of its tokens in circulating supply:

| Supply              | Amount                |
|---------------------|-----------------------|
| Initial Supply      | 31.8 billion ADA      |
| Circulating Supply* | 33.93 billion ADA[^5] |
| Max Supply          | 45 billion ADA        |

'* The top 100 addresses on network hold ~17% circulating supply.

Expansion of the circulating supply comes from the *reserve*, where `reserve = max supply - total supply` and
`total supply = ADA in circulation plus ADA in treasury`. Expansion is non-linear, greater amounts released during
first years but decreases over time until most rewards will come from transaction fees. The supply schedule can 
therefore be described as monotonically decreasing inflation.

![img_2.png](img_2.png)
Source: https://forum.cardano.org/t/how-does-cardano-reach-its-supply-cap-via-staking/39697/8

### Rewards
Stake pools earn block rewards in the form of *expansion* and *fees*, which are shared between the stake pool operator
and the stakers which delegated to the pool. Stake pool operators take a commission for running staking pools.

0.3% of the reserve is distributed each epoch, as staking rewards and treasury funding: 80% to stake pool 
operators/delegators and 20% to the treasury. The treasury (aka 'pot') is used for funding projects, improvements 
and the long term sustainability of Cardano.

Rewards will therefore ultimately be comprised of transaction fees only, once the reserve supply has been depleted.

#### Staking (WIP):

Pool Mechanics:
* Fixed cost of 340 ADA per pool, covering operating costs
* **Margin**: operator commission fee
* **Pledge amount**: validators own stake and commitment to the pool
* **Saturation Parameter** (parameter "k"): defines how many pools and estimated cap of stake to guarantee
  decentralisation
* No rewards on excess stake above cap, forcing large operators to create many pools which compete. Saturation point ~68m ADA
* Delegators will move to another pool if operator does not behave in interests of protocol
  * Snapshot of participants at each epoch (and used with delay of one epoch), so operator can lose power within 2
    epochs (10 days)

Delegators:
* Other factors to be considered by the staker:
  * pool performance: a stake pool operator which misses slots is missing out on rewards, which are shared with
    those stakers delegated to the pool
  * decentralisation:
  * fees: fixed fees (amount taken from total epoch rewards) and margin (amount taken from total epoch rewards after
    fixed fees deducted, used to cover pool running costs). The remaining rewards are distributed to stakers.

TODO
- pool operators set own fees
- 3-5% APY staking reward for delegators
- 24.5b ADA staked across ~3200 pools (~70% circulating supply), with ~1.1m delegators[^3]
- designed to be decentralised through saturation parameter ("parameter K"), whereby pool has a saturation point
  (cap) at which it no longer earns rewards
- 80/20
  - todo - does the 20/80 split make sense?
- No lock-up/unbounding period (3 epoch initial latency period)

## Economic Incentives
Cardano has aligned its economic incentives to encourage decentralization, which it deems as critical to the long-term
success of the project. Rewards are therefore shared between delegators and stake pool operators, a symbiotic
relationship maximising rewards so long as they are rational (Nash equilibrium).

This design also leverages economic specialisation: stake pool operators have the time, technical expertise and 
sufficient capital to run nodes which secure the network. Delegators may have none of these, instead delegating 
their stake to a stake pool, thereby increasing the overall stake and increasing the probability of the stake pool 
being elected to earn block rewards.

Cardano's incentive mechanism seeks a balance across staking pools, where an equilibrium means that rewards are 
optimal for all when stake delegated evenly across pools. A cap on stake pool size 

* Staking pool operators are incentivized to remain online in order to be elected as a slot leader, thereby being
  granted the right to produce a block and claim the corresponding reward.
* **Saturation Point** (parameter *k*): stake pools have a cap at which point they no longer earn rewards, incentivizing
  the creation of new pools.

Stake pools can determine own commission rates and stakers can delegate their stake to any staking pool with no
  lock-up period. This means they are free to switch to another pool at any time, should a pool with a more
  attractive rate become available. This leads to a natural market equilibrium as stakers delegate to pools with the
  most favourable rates.

![img_3.png](img_3.png)

* Perfect competition: stake pools arrange until an equal distribution across pools
* No slashing: protocol incentivizes validators to stay honest and online. Penalisation of malicious participants
  unnecessary provided desired number of pools exist, and they are in Nash equilibrium[^6]

## Pros and Cons

* Rewards shared between stake pool operators and delegators, no lock up period so delegators can easily re-stake with
  another operator if a stake pool performs poorly or its operator behaves maliciously (liquid democracy).
* No slashing, reducing delegator staking risk.

---
### Footnotes
[^1]: https://cardanians.io/en/the-story-of-ada-lovelace-40
[^2]: The accounting model is extended to accommodate transactions using custom token types (with their own monetary
policy), without the need for smart contracts. Multiple token types can be included within the same transaction. https://github.com/input-output-hk/cardano-ledger/blob/master/doc/explanations/features.rst
[^3]: https://www.figment.io/resources/cardano-ada-tokenomics
[^4]: https://www.cryptoeq.io/corereports/cardano-abridged
[^5]: https://messari.io/asset/cardano/chart/sply-circ
[^6]: https://medium.com/coinmonks/why-cardano-does-not-need-slashing-85630ff55092