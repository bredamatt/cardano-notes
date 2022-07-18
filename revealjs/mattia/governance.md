# Governance

Governance in the blockchain space could mean many different things, but in this case, it refers specifically to how the community is capable of "steering" the evolution of the blockchain system. 

One way we can assess the "value" of a particular governance model is to use the more recently devised Blockchain Governance framework from IOHK: [Blockchain Governance](https://arxiv.org/pdf/2201.07188.pdf)

In this paper, there are 7 properties we can base our evaluation on:

1. Suffrage
2. Pareto Efficiency
3. Confidentiality
4. Verifiability
5. Accountability
6. Sustainability
7. Liveness

## Suffrage

*"The right to participate
in decision making procedures."*

Can be established for a blockchain governance system various ways:

- mining based (hashing power)
- token based (token owenership)
- identity based (identity verification)

## Pareto Efficiency

*"A blockchain governance system is Pareto efficient if whenever a decision-making process is held, alternative X cannot win if there exists another alternative Y that is preferred by at least one participant and no participant prefers X over Y."*

Think of this as the outcome of a voting process being the "best" possible outcome of the set of outcomes that could occur.

## Confidentiality

- Type 1: "Secrecy":

*"A blockchain governance system satisfies secrecy if whenever a decision-making process is held, an adversary cannot guess the input of any participant better than an adversarial algorithm whose only inputs are the overall tally and, if the adversary is a participant, the adversary’s input."*

- Type 2: "Pseudonymity":

*"A blockchain governance system satisfies pseudonymity if no participant is required to reveal their real-life identity to participate in the decision-making processes"*

Where Type 1 is stronger than Type 2. 

## (End-to-End) Verifiability

*"A blockchain governance system is verifiable if whenever a decision-making process takes place, participants are able to verify their inputs were properly tallied and independent observers are able to verify that inputs from eligible participants were properly tallied."*

Usually, split between:
- individual (voter can verify their vote was created, stored and tallied correctly)
- global (everyone can verify that only valid votes are in the ballot box, and that all stored votes are properly tallied)

## Accountability

*"A blockchain governance system satisfies the property of accountability if whenever participants bring in a change, they are held individually responsible for it in a clearly defined way by the platform."*

Think of this as "Skin-in-the-Game".

## Sustainability

- Type 1: "Development":
*"A blockchain governance system sustains development if it incentivises, via monetary rewards or otherwise, participants who develop successful improve ment proposals for the platform"*

- Type 2: "Participation":
*"A blockchain governance system sustains participation if it incentivises, via monetary rewards or otherwise, participants who participate in the decision-making process of the platform"*

## Liveness

*"A blockchain governance system satisfies liveness if it is capable of incorporating an input of urgency from the stakeholders and then being capable of acting on it in the sense that if an issue is deemed to be urgent according to some function, then the decision making procedure is capable of terminating within a reasonable amount of time, as a function of the urgency of the matter."*

<!-- 
Potential Attack Vector or Denial of Service:
  - The committee members commit the seed onchain
  - Majority go offline before the next pre-voting epoch
  - The seed for the next round of voting is not decrypted
  - The voting halts, and no new proposals can be created
  - The system is not crash tolerant
  - The system does not have any liveness proofs
-->


## Approach

We will now attempt to analyse the Cardano Blockchain Governance system according to these definitions.

## Terminology

To understand the governance terminoloy in Cardano better, let us break down some important terms.

### Proof-of-Stake

In Cardano's governance system, voting power is proportial to *stake*.

Stake can be defined as: "number of tokens locked to a particular voting round".

### Proposer

A community member who proposes a project. Projects also need to go through a proposal review process (which is off-chain).

### Voters

Community members, who decides to vote on a project. They do this by depositing an amount of Ada (Cardano native-token). 

They are incentivized to deposit more within a voting round whenever they see proposals they are interested in.

### Experts

A community member, who declares him/herself as an expert on a particular topic and receives "delegated stake".

This is a particular type of staking mechanism which lets voters delegate their voting power to an expert, without sending his/her coins to them directly.

### Committee

A (*partially*) randomly chosen "special" voter (for example someone who has deposited a large stake), which is in charge of tallying and executing the votes. 

The likelihood of being selected as a committee member is propotional to the amount of stake a particular voter has deposited, but all randomly chosen committee members, must also confirm their position on the committee with a special transaction.

### Treasury

As mentioned, Cardano uses a treasury system to govern the evolution of the protocol. The treasury can be seen as a fund for collective decision making purposes.

### Funding

The treasury is funded in three different ways:

- when new blocks are minted, a proportion of the reward goes to the treasury
- miners' rewards are taxed, and the tax is collected to the treasury
- donations, or charity are also possible venues of funding

## Collective Decision Making

The way the treasury funds are spent, is decided via a collective decision making process, split up into three epochs:

1. Pre-voting epoch,
2. Voting epoch, and
3. Post-voting epoch

### Pre-voting epoch

During the pre-voting epoch, the proposers submit a set of proposals which need to be voted on.

It is important to note that only one CIP (Cardano Improvement Proposal) can be proposed at a time, whereas multiple FP's (Funding Proposals) can be proposed at the same time.

Additionally, it is at this stage that voters and experts register for the voting round using specific transactions. 

Theoretically there is a certain, but unidentified, desirable amount of experts per round, because there is a threshold: 

$$ \beta_{min} $$
 
which defines the maximum stake rewards an expert can obtain from a particular round.  This raises some questions around the Pareto efficiency of the decision making process since "experts" related to a particular proposal are disenctivized from paricipating with majority stake.

However, both experts and voters have to stake to join a voting round, which implies that only those interested in a particular outcome would put in the skin in the game, and therefore prevent "no-stake-attacks".
 
### Voting epoch

During the voting epoch, the voting committee is first selected with a random probability on a set mathematical inequality, which incorporates the use of the random seed generated by the previous voting committee. This random seed is generated using a hierarchical deterministic algorithm.

After the committee generates a voting key using a decentralized threshold key-generation algorithm, the voters cast votes, which can be of three forms:

$${Yes, No, Abstain }$$

### Post-voting epoch

During the post-voting epoch, each voting committee member will post the encrypted form of a part of the group $$\mathbb{G}$$

### Liquid democracy

A liquid democracy is a combination of a direct, and representative democracy. In a direct democracy, everyone votes for every proposal. In a representative democracy, all voters vote for representative, who make all the decisions. In a liquid democracy, all voters can voters can vote directly on a proposal, or they can delegate their votes to an expert. This is useful in scenarios when a voter does not necessarily know enough about a particular proposal, and wants their voting weight, as votes are determined by the amount of Ada staked, to be delegated to someone the voter believes to be more knowledgable about a particlar project.

### Delegated Proof-of-Stake

### Cryptographic primitives

The primitives used in governance are highlighted [here](../Cryptography.md)


### Answers to the questions

2 things we liked about the Cardano Blockchain Governance system:
- Liquid democracy (the ability to delegate votes to an expert)
- The commit-reveal mechanism which allows the committee to generate a random seed for the next round of voting

2 things we disliked about the Cardano Blockchain
- The lack of a mechanism to prevent our potential attack vector
