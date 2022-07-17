# Tokenomics

TODO: alternative currencies possible on CSL
TODO: 2 pros 2 cons

Native coin: ADA
Network economics:
* Staking 
* Fees 
* Governance

Total supply: 45 billion
In circulation: 33.5 billion

At genesis block distribution:
Public Sale: 25.9 billion ADA - (57.6%)
Reserve: 13.9 billion ADA - (30.9%)
IOHK: 2.46 billion ADA - (5.5%)
EMURGO: 2.07 billion ADA -  (4.6%)
Cardano Foundation: 640 million ADA - (1.4%)

0.3 % of the reserve (supply - in circulation) per epoch (every 5 days). Where 80 % is a reward for the stake pool, 20
% is for the treasury.

# Delegated Proof-Of-Stake 

New blocks are being produced by stake pools. A stake pool is a reliable server node that focuses on ledger maintenance and holds the combined resources -the 'stake'- of various stakeholders, delegators, in a single entity. Pledge is the only pool parameter that increases rewards. The stake pool operator (SPO) asks commission from the delegators.

## Pledging 
Stake pool operators can pledge their own ADA to the pool to make it more attractive to people that want to delegate. The higher the pledge, the higher the reward for the pool. Every 500k pledge increase means delegates will receive ≈ 0.008% APY MORE rewards. The pledge is not part of the stake of the stake pool.

## Delegating
Delegators delegate their stake to a staking pool and get rewarded proportionally to their stake. There is a latency period of 15-20 days. Delegators hold their spending power

## Pool mechanics
Stake pools are rewarded by:
- Fixed costs - a fixed fee of 340 ADA to every pool. It technically covers the pool's operating costs.
- Transaction fees - fees from every transaction from all blocks produced during every epoch go into a virtual 'pot'. A fixed percentage (0,3%) of the remaining ada reserves is added to that pot.
- Monetary expansion - a certain percentage (20%) of the pot is sent to the treasury, and the rest is used as epoch rewards (80%).

### Price discovery transaction fees 
Fees are constructed around two constants (a and b). The formula for calculating minimal fees for a transaction (tx) is:
a * size(tx) + b

- a: reflects the dependence of the transaction cost on the size of the transaction. The larger the transaction, the more resources are needed to store and process it.
- b: is a payable fee, regardless of the sthanksize of the transaction. This parameter was primarily introduced to prevent
Distributed-Denial-of-Service (DDoS) attacks. b makes such attacks expensive, and eliminates the possibility of an attacker generating millions
of small transactions to flood and crash the system.
- size(tx): is the transaction size in bytes

# Incentives
## Decentralization incentives
Stake pools have a maximum total stake amount which is determined by a parameter K. K defines how many pools there should be in the network and an estimated cap for their respective stake. Any amount of stake that surpasses this stake won’t earn additional reward.

## Governance incentives
For every post-voting epoch, 20% of the treasury fund will be distributed between voting committee members, experts and voters.

The fvoting committee members will receive a ixed amount upon completing their required actions in the next voting epoch.

The voters and experts will be rewarded regardless of the outcome of the vote, voters in proportion to their own stake, experts in proportion to the amount to their received delegations.


### Market equilibrium: see tokenomics and stake pools

#### Economic specialization: 
governance, keeping the network alive and potentially more with the possibility to write smart contracts on the csl/ccl?

#### Game theoretical models: (just wrote some stuff down which we could use, not entirely sure for me what they want to see here) 
equilibrium
public good game
tragedy of commons

#### Auction mechanics: 
As far as I know there are none

## Smart contracts
### Collateral
TODO