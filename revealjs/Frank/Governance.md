# Governance

---

**Goal:** Evaluate the use of governance in this project; name at least two things you like and two things you would want to improve.

---
## Collective Decision Making
How does this project solve the collective decision making problem?

"A treasury system is a community controlled and decentralized collaborative decision-making mechanism for sustainable funding of the underlying blockchain development and maintenance."

### Treasury
The primary goal of the treasury is to "resolve funding sustainability for long term development and maintenance"[^1]. 

* Voting power proportional to stake
* "Engaged community is better than a passive one. As a result, holders of ADA become willing evaluators of decisions and policies through staking, which results in improved community-wide support for decisions reached."
* Potentially funded via: 1) taxation on block rewards (sustainable provided block rewards remain, could fluctuate over time), 2) minting new ADA (start of each new treasury period, causing inflation) and 3) donations (unsustainable)
  * Based on ZCash: treasury takes percentage of miners reward
  * 20% of rewards of epoch, 20% of monetary expansion of each epoch, donations
* **Liquid democracy (delegated democracy)**: stakers can vote *directly * or delegate to *domain experts *
  * Hybrid of direct democracy and representative democracy
  * Anyone can submit proposal for project funding, only a few can be supported due to limitation of funds. Proposals categorised and funding allocated by category
* Voting model: YES, NO, ABSTAIN
  * Fuzzy threshold voting shows advantages of this scheme for treasury application
* Proportion of treasury fund rewards voting *committee members*, *voters * and *experts *
* Agreement measures:
  * Consensus measure - measure of agreement among all participants
  * Proximity measure - measure of agreement between individual solutions and collective solution
* Treasury period: 
  * pre-voting epoch (project proposals submitted, voters/experts registers), 
  * voting epoch (committee selected, voting key generated, voters/experts cast ballots),
    * Voting power proportional to (delegated) stake
    * Stake ownership verification system
  * post-voting epoch (committee computes and signs treasury decision), Winning proposals then funded
* Funding proposal voting currently off-chain, via Project Catalyst on Ideascale platform https://cardano.ideascale.com

* community-controlled treasury system, funded by minting coins, a share of block rewards and transaction fees
* "Decentralised treasury, funded from monotonically decreasing inflation and transaction fees".
* Any user can request funds by ballot, voted on by CSL stakeholders
* "social contract"

## Governance Structures
What are the structures of governance in this project? How are changes proposed and voted on?

Cardano aims to be decentralized as a "core value", but currently relies on traditional co-ordination mechanisms for 
governance until the planned on-chain treasury system is implemented in the Voltaire Era [^1].

### Improvement Proposals
- Improvement proposals are currently managed via a Cardano Improvement Proposals (CIP) [^2]

### Funding Proposals

#### Project Catalyst
A stop-gap solution for proposing projects for funding, using the IdeaScale platform[^3], with some similarities to 
the final on-chain treasury system:
- ADA holders propose projects by connecting Daedalus wallet or Catalyst voting app
- Stakeholders register to vote on a proposal, where voting power weighted to ADA held 

#### Voltaire
The Voltaire Era will introduce an on-chain treasury system which:

  - todo: go into specifics
  - Funding Proposals

## Voting Mechanisms
What voting mechanisms are used in this project?
Who is allowed to vote in this project? What are the voting criteria?

- Treasury-based: funding discussions create social contract
- Plans for chain-based system to propose/vote on trusted data feeds and soft/hard forks - reducing disagreements and fractured communities
- delegated stakers and staking pool operators are able to vote by staking ADA?
- domain experts

## Pros & Cons
Name at least two things you like and two things you would want to improve.

---
### Footnotes
[^1]: https://emurgo.io/what-makes-the-cardano-blockchain-treasury-system-special/
[^1]: A Treasury System for Cryptocurrencies: https://eprint.iacr.org/2018/435.pdf
[^2]: https://cips.cardano.org
[^3]: https://cardano.ideascale.com/c/
