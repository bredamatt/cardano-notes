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

*"A blockchain governance system is Pareto efficient
if whenever a decision-making process is held, alternative X cannot
win if there exists another alternative Y that is preferred by at least
one participant and no participant prefers X over Y."*

Think of this as the outcome of a voting process being the "best" possible outcome of the set of outcomes that could occur.

## Confidentiality

Type 1: "Secrecy":

*"A blockchain governance system
satisfies secrecy if whenever a decision-making process is held, an
adversary cannot guess the input of any participant better than an
adversarial algorithm whose only inputs are the overall tally and, if
the adversary is a participant, the adversary’s input."*

Type 2: "Pseudonymity":

*"A blockchain governance system satisfies pseudonymity if no participant is required to
reveal their real-life identity to participate in the decision-making
processes"*

Where Type 1 is stronger than Type 2. 

## (End-to-End) Verifiability

*"A blockchain governance system is verifiable if whenever a decision-making process
takes place, participants are able to verify their inputs were properly
tallied and independent observers are able to verify that inputs from
eligible participants were properly tallied."*

Usually, split between:
- individual (voter can verify their vote was created, stored and tallied correctly)
- global (everyone can verify that only  )


## Accountability



## Sustainability

## Liveness

## Terminology

To understand the governance terminoloy in Cardano better, let us break down some important terms:

- Proposer: a community member who proposes a project
- Voter: a community member, who decides to vote on a project
- Expert: a community member, who declares him/herself as an expert on a particular topic and receives "delegated stake"
- Committee member: a (partially) randomly chosen voter, which is in charge of executing the voting process

### Proposers

### Voters

### Committee


## Treasury

As mentioned, Cardano uses a treasury system to govern the evolution of the protocol. The treasury can be seen as a fund for collective decision making purposes. 

### Funding

The treasury is funded in three different ways:

- when new blocks are minted, a proportion of the reward goes to the treasury
- miners' rewards are taxed, and the tax is collected to the treasury
- donations, or charity

## Collective Decision Making

The way the treasury funds are spent, is decided via a collective decision making process, split up into three epochs:

1. Pre-voting epoch,
2. Voting epoch, and
3. Post-voting epoch

### Pre-voting epoch

During the pre-voting epoch, the proposers submit a set of proposals which need to be voted on.

### Voting epoch

During the voting epoch, the voting committee is selected by
!!insert-fancy-method-here!!. The committee generates a voting
key and the voters cast votes.

### Post-voting epoch

During the post-voting epoc, eah voting committee member will post the encrypted form of a part of the group $$\mathbb{G}$$

### Liquid democracy

A liquid democracy is a combination of a direct, and representative democracy. In a direct democracy, everyone votes for every proposal. In a representative democracy, all voters vote for representative, who make all the decisions. In a liquid democracy, all voters can voters can vote directly on a proposal, or they can delegate their votes to an expert. This is useful in scenarios when a voter does not necessarily know enough about a particular proposal, and wants their voting weight, as votes are determined by the amount of Ada staked, to be delegated to someone the voter believes to be more knowledgable about a particlar project.

### Delegated Proof-of-Stake

### Cryptographic primitives

The primitives used in governance are highlighted [here](../Cryptography.md)