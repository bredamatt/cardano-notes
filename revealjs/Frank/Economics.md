# Economics

---

**Goal:** Evaluate the use of tokenomics in this project; name at least two things you like and two things you would want to improve.

* Use at least 3 of the following economic concepts in your answer:
  * Market Equilibrium (Supply and Demand):
    * What is the supply schedule of the token, does it have inflation or deflation?
    * Who will want to use the coin, and for what?
  * Economic Specialization
  * Game Theoretical Models
  * Auction Mechanics and Price Discovery Methods

---

## Tokenomics

### Native Token
The native token is ADA, named after Ada Lovelace, an English mathematician[^1], which is used for fees, rewards
and deposits.

Cardano does also have multi-asset support via "native tokens"[^2], but usage does not have any direct economic impact on
the network.

### Tokenomics:

#### Token Usage

* **Staking**: ADA stakers delegate to stake pools and earn rewards for securing the network. No
  lock-up/unbounding period (3 epoch initial latency period)
* **Fees**: transaction fees paid in ADA
* **Governance**: ADA stakers participate in governance and vote on CIPs

#### Supply

| Supply              | Amount                |
|---------------------|-----------------------|
| Initial Supply      | 31.8 billion ADA      |
| Circulating Supply* | 33.93 billion ADA[^5] |
| Max/Total Supply    | 45 billion ADA        |

'* The top 100 addresses on network hold ~17% circulating supply.

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

### Rewards
Stake pools earn block rewards in the form of *expansion* and *fees*, which are shared between the stake pool operator
and the delegated stakers in the pool. Stake pool operators earn commission for running staking pools.

Expansion comes from the *reserve*, where `reserve = total supply - max supply` and
`total supply = ADA in circulation plus ADA in treasury`. Expansion is non-linear, greater amounts released during
first years but decreased over time until most rewards will come from transaction fees.

0.3% of the reserve is distributed per epoch (5 days) as staking rewards and treasury funding, 80% to staking
operators and delegators and 20% to treasury. Treasury (aka pot) used for funding projects, improvements and the long
term sustainability of Cardano.

* Annual inflation of ~2%
* Monotonically decreasing inflation (todo: describe reduction in block rewards)
* 3-5% APY staking reward for delegators

#### Staking:
- pool operators set own fees
- 24.5b ADA staked across ~3200 pools (~70% circulating supply), with ~1.1m delegators[^3]
- designed to be decentralised through saturation parameter ("parameter K"), whereby pool has a saturation point
  (cap) at which it no longer earns rewards
- 80/20
  - todo - does the 20/80 split make sense?

## Economic Incentives
Cardano has aligned its economic incentives to encourage decentralization, which it deems as critical to the long-term
success of the project. Rewards are therefore shared between delegators and stake pool operators, a symbiotic
relationship maximising rewards so long as they are rational (Nash equilibrium).

* Cardano's incentive mechanism seeks a balance across staking pools, where an equilibrium means that rewards are
  optimal for all when stake delegated evenly across pools.
* Staking pool operators are incentivized to remain online in order to be elected as a slot leader, thereby being
  granted the right to produce a block and claim the corresponding reward.
* Saturation Point (parameter k): stake pools have a cap at which point they no longer earn rewards, incentivizing
  the creation of new pools.
* Stake pools can determine own commission rates and stakers can delegate their stake to any staking pool with no
  lock-up period. This means they are free to switch to another pool at any time, should a pool with a more
  attractive rate become available. This leads to a natural market equilibrium as stakers delegate to pools with the
  most favourable rates.
* Other factors to be considered by the staker:
  * pool performance: a stake pool operator which misses slots is missing out on rewards, which are shared with
    those stakers delegated to the pool
  * decentralisation:
  * fees: fixed fees (amount taken from total epoch rewards) and margin (amount taken from total epoch rewards after
    fixed fees deducted, used to cover pool running costs). The remaining rewards are distributed to stakers.
* Perfect competition: stake pools arrange until an equal distribution across pools
* No slashing: protocol incentivizes validators to stay honest and online. Penalisation of malicious participants
  unnecessary provided desired number of pools exist, and they are in Nash equilibrium[^6]

### Pool Mechanics
* Fixed cost of 340 ADA per pool, covering operating costs
* **Margin**: validator commission fee
* **Expansion**: ~0.3% of reserve per epoch as staking rewards
* **Pledge amount**: validators own stake and commitment to the pool
* **Saturation Parameter** (parameter "K"): defines how many pools and estimated cap of stake to guarantee
  decentralisation
* No rewards on excess stake above cap, forcing large operators to create many pools which compete. Saturation point ~68m ADA
* Delegators will move to another pool if operator does not behave in interests of protocol
  * Snapshot of participants at each epoch (and used with delay of one epoch), so operator can lose power within 2
    epochs (10 days)

# Pros and Cons
Name at least two things you like and two things you would want to improve.

* Rewards shared between pool operators and delegators, no lock up period so delegators can easily re-stake with
  another operator (voting) if operator behaves maliciously.
* No slashing, reducing delegator staking risk

---
### Footnotes
[^1]: https://cardanians.io/en/the-story-of-ada-lovelace-40
[^2]: The accounting model is extended to accommodate transactions using custom token types (with their own monetary
policy), without the need for smart contracts. Multiple token types can be included within the same transaction. https://github.com/input-output-hk/cardano-ledger/blob/master/doc/explanations/features.rst
[^3]: https://www.figment.io/resources/cardano-ada-tokenomics
[^4]: https://www.cryptoeq.io/corereports/cardano-abridged
[^5]: https://messari.io/asset/cardano/chart/sply-circ
[^6]: https://medium.com/coinmonks/why-cardano-does-not-need-slashing-85630ff55092