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

These definitions will be discussed loosely as we evalaute the different components that constitute the Cardano governance system. But first, let us define why we need a governance system.

## Purpose

For any ecosystem to have a sustainable future, it is necessary to govern a system's evolution. Yet the key point, is to figure out where the ecosystem is evolving (to something better, or worse?).

It is quite common to state that the purpose of a governance system is to maximize the utility of its participants. It follows that we need to know what the utility function of a participant in the community would be, but for now we can simply state it is about a positive evolution of the Cardano ecosystem. An example of this would be when meaningful projects and use-cases are implemented on the Cardano blockchain. 

In general, governance problems arise whenever it becomes rational for an individual actor to game / play the system for his/her own benefit at the expense of the common good of the community. Hence, we could say that a particular governance system is good only as far as it makes it rational for system participants to act in the interest of the common good. In other words, a well-designed governance mechanism would also be capable of incentivizing agents, or at least indirectly making them act in the interest of the common good, even when it may initially appear rationally not to.

The above points are important to take into consideration when assessing the Cardano governance mechanism with respect to the Blockchain Governance definitions below.

## Blockchain Governance definitions

### 1. Suffrage

*"The right to participate
in decision making procedures."*

Rights provied in various ways:

- mining based (hashing power)
- token based (token owenership)
- identity based (identity verification)

### 2. Pareto Efficiency

*"A blockchain governance system is Pareto efficient if whenever a decision-making process is held, alternative X cannot win if there exists another alternative Y that is preferred by at least one participant, and no participant prefers X over Y."*

Think of this as the outcome of a voting process being the "best" possible outcome of the set of outcomes that could occur.

### 3. Confidentiality

- Type 1: "Secrecy":

*"A blockchain governance system satisfies secrecy if whenever a decision-making process is held, an adversary cannot guess the input of any participant better than an adversarial algorithm whose only inputs are the overall tally and, if the adversary is a participant, the adversary’s input."*

- Type 2: "Pseudonymity":

*"A blockchain governance system satisfies pseudonymity if no participant is required to reveal their real-life identity to participate in the decision-making processes"*

Where Type 1 is stronger than Type 2. 

### 4. (End-to-End) Verifiability

*"A blockchain governance system is verifiable if whenever a decision-making process takes place, participants are able to verify their inputs were properly tallied and independent observers are able to verify that inputs from eligible participants were properly tallied."*

Usually, split between:
- individual (voter can verify their vote was created, stored and tallied correctly)
- global (everyone can verify that only valid votes are in the ballot box, and that all stored votes are properly tallied)

### 5. Accountability

*"A blockchain governance system satisfies the property of accountability if whenever participants bring in a change, they are held individually responsible for it in a clearly defined way by the platform."*

Think of this as "Skin-in-the-Game". Parties participating in the governance system are incentivized to do good because they themselves are accountable for their own profits/rewards for doing so.

### 6. Sustainability

- Type 1: "Development":
*"A blockchain governance system sustains development if it incentivises, via monetary rewards or otherwise, participants who develop successful improvement proposals for the platform"*

- Type 2: "Participation":
*"A blockchain governance system sustains participation if it incentivises, via monetary rewards or otherwise, participants who participate in the decision-making process of the platform"*

### 7. Liveness

*"A blockchain governance system satisfies liveness if it is capable of incorporating an input of urgency from the stakeholders and then being capable of acting on it in the sense that if an issue is deemed to be urgent according to some function, then the decision making procedure is capable of terminating within a reasonable amount of time, as a function of the urgency of the matter."*

<!-- 
Potential Attack Vector or Denial of Service:
  - The committee members commit the seed onchain
  - Majority go offline before the next pre-voting epoch
  - The seed for the next round of voting is not decrypted
  - The voting halts, and no new proposals can be created
-->


## Exploring Cardano's Governance system

To understand the governance terminology in Cardano better, let us break down some important concepts. 

### Funding Proposals vs Cardano Improvement Proposals

Cardano's governance system consists of:
- The Cardano community (decentralized)
- The Cardano Foundation (more centralized)

The first caveat we discovered was that there are two different types of proposals in the Cardano ecosystem:

- Cardano Improvement Proposals (CIPs), and
- Funding Proposals (FP)

The CIPs are entirely managed by the Cardano Foundation, whereas solely FPs are eligible for the community to decide upon. This indicates that there is to some degree an aspect of centralization remaining in Cardano's governance system, at least the protocol layer. It has been mentioned, nevertheless that eventually, CIPs will also be governed by the community, but it is unclear when. Regardless of the truthfulness of the latter statement, it is near impossible to claim that the decision to make CIPs subject to public voting is made in a decentralized manner. This being said, we have to restrict the analysis of the governance process to FPs accordingly.

### Proposals

To contribute to the sustainable evolution of the Cardano ecosystem, community members are eligible to submit proposals. These proposals represents projects to be built on top of the Cardano blockchain.

Generally, all system participants may have ideas about how the system should evolve, but not all of them may know what is in their best interest. Nevertheless, one would argue, that as a participant in a system, one immediately has "skin-in-the-game" in that system since it directly effects the person's utility.

The most obvious incentive for community members to participate in the Cardano ecosystem is to make the Cardano ecosystem better. What this "better" implies, however, is not very clear. The most obvious definition would be "better in such a way that the underlying native token of Cardano, namely ADA, surges in value", thereby increasing the financial position of the community member. There may be purely altruistic motives, or community members with an interest in solving difficult enginereering problems (we do not exclude such participants here).

As we learned from the collective decision making games in class, even if on the average it is rational to contribute to common good, there are occassions where it is more rational to deviate. Here, rationality implies making a decision that maximizes the decision maker's utility rather than that of the collective. This is also important to take into consideration, when considering the extent to which the good of the community has a positive impact on the individual's utility. In a Blockchain scenario, the most common binder between an individual actor, and the community itself, is its underlying token. Hence, any person deciding to join the commuinity may have good intentions, but may nevertheless face a scenario where it is more beneficial to deviate, such as for example disrupting a positive project, when a short position on the tokens value exists. ...But, because stake in the system is relative to the amount of ADA tokens a particular community member holds, it would arguably make the most sense that there are financial incentives at play, and that these financial incentives prevent adversarial behavior. 

### Evaluating Project Catalyst

A core question we tried to answer, was "where do I as a future community member, create / propose a project in the Cardano ecosystem?". In practice, this can be done with [Project Catalyst](https://projectcatalyst.org/), an online platform where community members can learn about how to come up with their own proposals, vote, and assess proposals.

It was important for us to see how easy it was to sign up to, and participate in the Cardano Community. We signed up to Project Catalyst as a standard user so we could evaluate the governance system's practicalities in more detail. Signing up was quite straightforward, as we just signed up with an email address. 

Unfortunately, we were unable to propose a new project because the deadline had passed, but there was a well-defined interface for doing so, and we quickly found out the different stages/rounds from project ideation to funding a particular "governance round" consists of. These were:

- Proposal
- Review
- Finalize
- Assessment
- Assess QA
- Governance 

It is also worthwhile mentioning that there is a term called "Campaigns" which represents group of proposals with a common theme. Proposals must belong to a particular campaign accordingly.

For the sake of brevity, we will concentrate primarily on Governance, but it is necessary to briefly cover what the different periods represent.

*Proposal period*:
- A fixed period of time where project proposals are welcome

*Proposal review period*
- A fixed period of time where proposals are reviewed 

*Proposal finalization period*
- A fixed period of time where proposals are finalized and prepared for assessment

*Proposal assessment period*
- A fixed period of time where proposals are assessed by project assessors

*Assessment Quality Assurance period*
- A fixed period of time where the quality assurance of the assessment period is established

*Governance period*
- A fixed period of time, divided into three epochs:
  - Pre-voting epoch
  - Voting epoch
  - Post-voting epoch

Inactive proposals are eventually archived.

### Treasury funding

As mentioned, Cardano uses a treasury-model for collective decision making purposes.

Currently, Cardano's treasury system is in Funding round 9 (usually listed as FUND9). The data surrounding the treasury, and its overall funding history, is relatively transparent, but not necessarily easy to understand. The data is generally shared through a shared Google Doc, which is publicly readable, but terminology is defined across various information sources.

As mentioned, Cardano uses a treasury system to govern the evolution of the protocol. The treasury can be seen as a fund for collective decision making purposes. The treasury is funded in three different ways:

1. when new blocks are minted, a proportion of the rewards goes to the treasury
2. miners' rewards are taxed, and the tax is collected to the treasury
3. donations, or charity are also possible venues of funding

The funds in the treasury are thereafter used to fund proposals.

### Voters

These are community members who decides to vote on the projects proposed in a particular funding round. They do this by depositing an amount of ADA as a security deposit. The more they deposit, the more voting power they have. In other words, their "stake" is proportional to their voting power. Because voting power determines which proposals win, taking a huge risk in a particular voting rode by depositing a lot of stake, leads to "skin-in-the-game", and therefore also accountability. 

The voting power deposited within a particular funding round can also be delegated to one, or more experts. This way, voters can make the decision making more efficient by passing their voting power to someone more knowledgeable about the projects proposed in a particular funding round.

However, this also introduces a problem. Since voters are rewarded for participating in the community, and as this reward is proportional to their stake, this model leads to a "rich-gets-richer" scenario, which eventually could lead to a stronger degree of centralization than desirable. That being said, this model thus satisfies the sustainability of partcipation, as per the Blockchain governance framework listed above. Indeed, there would be no reason to participate in anything, if it didn't give you anything in return, and the extent to which this return is favorable, determines whether it is a sustainable model, or not. Therefore, we argue that the staking-based governance protocol used for voters is good. This is because it gives incentives to not only vote, but also to integrate more profoundly into the ecoysystems, by running nodes, creating proposals, and so forth.

### Experts

A community member, who declares him/herself as an expert on a particular topic. The experts receives "delegated stake", and can use this to have a strong say on which projects end up getting voted on, since delegated stake is accumulative.

It should also be noted that this type of delegative stake a particular type of staking mechanism which lets voters delegate their voting power to an expert, without sending his/her coins to them directly.

### Committee

A (*partially*) randomly chosen "special" voter (for example someone who has deposited a large stake), who is in charge of tallying votes.

The likelihood of being selected as a committee member is propotional to the amount of stake a particular voter has deposited. Nevertheless, all randomly chosen committee members must also confirm their position on the committee with a special registration transaction. 

## Collective Decision Making

The way the treasury funds are spent, is decided via a collective decision making process, split up into three epochs:

1. Pre-voting epoch,
2. Voting epoch, and
3. Post-voting epoch

### Pre-voting epoch

During the pre-voting epoch, the proposers submit a set of proposals which need to be voted on.

It is important to note that only one CIP (Cardano Improvement Proposal) can be proposed at a time, whereas multiple FP's (Funding Proposals) can be proposed at the same time.

Additionally, it is at this stage that voters and experts register for the voting round using specific transactions. 

Theoretically there appears to be some certain, but unidentified and hidden desirable amount of experts per round, because there is a threshold: 

$$ \beta_{min} $$
 
which defines the maximum stake rewards an expert can obtain from a particular round. This raises some questions around the Pareto efficiency of the decision making process since "experts" related to a particular proposal are disenctivized from paricipating with majority stake.

However, both experts and voters have to stake to join a voting round, which implies that only those interested in a particular outcome would place skin in the game, and therefore prevent "no-stake-attacks".
 
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