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

## 1. Suffrage

*"The right to participate
in decision making procedures."*

Rights provied in various ways:

- mining based (hashing power)
- token based (token owenership)
- identity based (identity verification)

## 2. Pareto Efficiency

*"A blockchain governance system is Pareto efficient if whenever a decision-making process is held, alternative X cannot win if there exists another alternative Y that is preferred by at least one participant, and no participant prefers X over Y."*

Think of this as the outcome of a voting process being the "best" possible outcome of the set of outcomes that could occur.

## 3. Confidentiality

- Type 1: "Secrecy":

*"A blockchain governance system satisfies secrecy if whenever a decision-making process is held, an adversary cannot guess the input of any participant better than an adversarial algorithm whose only inputs are the overall tally and, if the adversary is a participant, the adversary’s input."*

- Type 2: "Pseudonymity":

*"A blockchain governance system satisfies pseudonymity if no participant is required to reveal their real-life identity to participate in the decision-making processes"*

Where Type 1 is stronger than Type 2. 

## 4. (End-to-End) Verifiability

*"A blockchain governance system is verifiable if whenever a decision-making process takes place, participants are able to verify their inputs were properly tallied and independent observers are able to verify that inputs from eligible participants were properly tallied."*

Usually, split between:
- individual (voter can verify their vote was created, stored and tallied correctly)
- global (everyone can verify that only valid votes are in the ballot box, and that all stored votes are properly tallied)

## 5. Accountability

*"A blockchain governance system satisfies the property of accountability if whenever participants bring in a change, they are held individually responsible for it in a clearly defined way by the platform."*

Think of this as "Skin-in-the-Game". Parties participating in the governance system are incentivized to do good because they themselves are accountable for their own profits/rewards for doing so.

## 6. Sustainability

- Type 1: "Development":
*"A blockchain governance system sustains development if it incentivises, via monetary rewards or otherwise, participants who develop successful improvement proposals for the platform"*

- Type 2: "Participation":
*"A blockchain governance system sustains participation if it incentivises, via monetary rewards or otherwise, participants who participate in the decision-making process of the platform"*

## 7. Liveness

*"A blockchain governance system satisfies liveness if it is capable of incorporating an input of urgency from the stakeholders and then being capable of acting on it in the sense that if an issue is deemed to be urgent according to some function, then the decision making procedure is capable of terminating within a reasonable amount of time, as a function of the urgency of the matter."*

<!-- 
Potential Attack Vector or Denial of Service:
  - The committee members commit the seed onchain
  - Majority go offline before the next pre-voting epoch
  - The seed for the next round of voting is not decrypted
  - The voting halts, and no new proposals can be created
-->

## Terminology

To understand the governance terminology in Cardano better, let us break down some important concepts. 

A fundamental question to ask is what the *purpose* of a governance system.

### Purpose

For any ecosystem to have a sustainable future, it is necessary to govern a system's evolution. The only way to do this is to have a fair process where system participants are incentivized to act collectively for the common benefit. This is why we have decided to leverage the 7 definitions above as a framework for assessing Cardano's governance system.

In general, governance issues arise whenever it becomes rational for an individual actor to game / play the system for his/her own benefit at the expense of the common good. Hence, we could say that the value of a particular governance system is the extent to which it makes it rational to act in the interest of the common good.

### Proposals

Generally, all system participants may have ideas about how the system should evolve. One would argue, that as a participant in a system, one immediately has "skin-in-the-game" in that system - indeed the success of that system is dependent upon one's own contribution to it. Therefore, one could argue that we are naturally inclined to seek to benefit the systems we are a part of unless the cost of exploiting the system is cheap enough to make it more rational to do relative to improving it.

In Cardano, the ideas community members have for improving the Cardano ecosystem is defined as *proposals* here $P$, where there is a proposal $p_{i} \space, where \space i \in [0..N]$ for $N$ propsers. One way to think of these are as parameters to a "governance function" $\lambda(p_{i})$ taking as input the set of proposals $p_{i} \in P$. 

It is primarily $\lambda$ we are interested in evaluating in this section as it will by nature involve more technical goodies. 

Nevertheless it is important to check how easy it is to become a member in the first place to determine the extent to which the Cardano ecosystem incentivizes and grants an equal opportunity for community members to participate in the platform's evolution. In other words, we can assess both the sustainability and suffrage aspects of Cardano's governance model by looking into these aspects.

#### Funding Proposals vs Cardano Improvement Proposals

The first caveat we discovered was that there are two different types of proposals in the Cardano ecosystem:

- Cardano Improvement Proposals (CIPs), and
- Funding Proposals (FP)

The CIPs are entirely managed by the Cardano Foundation, whereas solely FPs are eligible for the community to decide upon. This indicates that there is to some degree an aspect of centralization remaining in the Cardano's governance system. This is regardless of the fact that Cardano has a significant amount of open source contribution. 

#### Becoming a community member

A core question is therefore, "where do I create / propose a project?". This is handled in practice with [Project Catalyst](https://projectcatalyst.org/), which creates an online platform where community members can learn about how to come up with their own proposals.

It was important for us to see how easy it was to sign up to the Cardano Community. We signed up to Project Catalyst as a standard user so we could evaluate the governance system's practicalities in more detail. This was quite straightforward, we just signed up with an email address, created a password, and verified our email address. Unfortunately, we were unable to propose a new project because the deadline had passed, but there was a well-defined interface for doing so, and we quickly found out the different stages from project ideation to funding, which consisted of:

- Proposal
- Review
- Finalize
- Assessment
- Assess QA
- Governance 
- Archive

For the sake of brevity, we will concentrate solely on the Governance 

#### Funding round 9

Currently, Cardano's treasury system is in Funding round 9 (usually listed as FUND9). The data surrounding the treasury, and its overall funding history, is relatively transparent, but not necessarily ideally visualised. The data is generally shared through a shared Google Doc, which is publicly readable.

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

### Cryptographic primitives

The primitives used in governance are highlighted [here](../Cryptography.md)

### Answers to the questions

2 things we liked about the Cardano Blockchain Governance system:
- Liquid democracy (the ability to delegate votes to an expert, and for experts to delegate their votes further as well)
- The commit-reveal mechanism which allows the committee to generate a random seed for the next round of voting

2 things we disliked about the Cardano Blockchain
- The lack of a mechanism to prevent our potential attack vector
- The fact that voting power is proportional to stake.