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

Currently, Cardano's treasury system is in Funding round 9 (usually listed as FUND9). The data surrounding the treasury, and its overall funding history, is relatively transparent, but not necessarily easy to understand. The data is generally shared through a shared Google Doc, which is publicly readable, but terminology is defined across various information sources making it not that straightforward to understand what the numbers mean.

As mentioned, Cardano uses a treasury system to govern the evolution of the protocol. Cardano was not the first platform to do so (the Dash governance system invented the treasury model). In a treasury system, the collective decides upon where funding goes. Hence, the amount of funds in the treasury becomes an important decision makign factor. 

In the Cardano governance system, the treasury is funded in three different ways:

1. when new blocks are minted, a proportion of the rewards goes to the treasury
2. miners' rewards are taxed, and the tax is collected to the treasury
3. donations, or charity are also possible venues of funding

The funds in the treasury are thereafter used to fund proposals.

### Voters
These are community members who decides to vote on the projects proposed in a particular funding round. They do this by depositing an amount of ADA as a security deposit. The more they deposit, the more voting power they have. Because voting power determines which proposals win, taking a risk in a particular voting round by depositing ADA, leads to "skin-in-the-game", and therefore also accountability. 

Still, it is possible that an inexperienced voter with large degree of stake disrupts the funding round by accidentally, or deliberately voting for a suboptimal proposal from a Pareto efficiency perspective. Yet, the extent to which voters with large stake would not want the best result for the collective is questionable since a bad outcome is something they themselves would be held accountable for. Additionally, there are opportunities to delegate stake to a funding round "expert", and this delegation mechanism is particularly valuable to give unknowledgable, but what may potentially be disruptive voters (by accident in this case) the ability to reach Pareto optimality to a greater extent.

In summary, it seems that the Cardano governance system implements *liquid democracy* to solve the problem of votes being passed **accidentally** to Pareto inefficient proposals. Because it is a choice whether to delegate, or not, there are *no guarantees* of Pareto efficiency as a consequence.

#### Voter rewards

Voters are rewarded proportional to the amount they deposited. As in traditional governance systems, this will naturally lead to a stronger degree of centralization with time since voters who deposit larger values are also rewarded accordingly. 

Generally, there is no clear logical conncetion between centralization and a lack of ecosystem sustainability. Many systems which are relatively centralized could exhibit sustainable behavior. Indeed, if the system's sustainability is harmed by centralisation, it tends to be a consequence of corrupt decision-makers rather than centralisation per se. In other words, ineffiency could be a indirect consequence of centralisation, but not always a direct one.

Furthermore, the exact cause of corruption is not always clear in centralised systemsd, but would generally be stated to be the outcome of there existing some rational decision existing which incentivizes an agent *enough* to deviate from the Pareto efficient goal for the collective. Thus, there could be some correlation between maximizing collective utility and decentralization as long as it is decentralized *enough*, where any central decision maker's swaying power does not provide *enough* guarantees for profiting from a deviation. Therefore, it is important that a governance system satisfies the suffrage definition, and makes participating in the protocol easy. As mentioned, it was very straightforward to sign up to Catalyst, and as it is possible to delegate to experts (see below).

However, suffrage per se is not representative enough as a measure of decentralization in the Cardano goverance system since voting power is based on the amount of ADA a particular voter deposits. That being said, a single voter would need to have a significant amount of ADA to skew the votes such that the result is in their favour, and the probability of one individual voter owning that much ADA is quite small (nevertheless possible). Alternatively, he/she would need to collude with a significant number of other voters to disrupt the Pareto efficent outcome of the funding round. Furthermore, this becomes less likely the more participants there are in the system. Recent figures indicate more than 250,000 participants in the last funding round, therefore we argue that it is difficult, to convince a significant enough number of participants to deviate from the collective good of Cardano's ecosystem once they signed up to it.

### Experts

As mentioned, Cardano uses a liquid democracy for their collective decision making. Experts are those voters who also receive "delegated stake". Therefore, if anyone has incentives to skew the vote, it would be experts with significant delegated stake since they would potentially have enough voting power to influence the funding round's outcome.

An interesting feature of the expert is that it also facilitates greater participation in the governance system, since anyone who holds some ADA can participate in the funding round, and simply delegate their votes to an expert. As such, it seems like a reasonable approach to guarantee participation sustainability as it lowers the knowledge barrier requirement for meaningful participation.

#### Expert rewards

Similarly to how voters are rewarded proportionally to their stake, experts are rewarded proportionally to the sum of their delegated stake. This means that to truly benefit as an expert in the Cardano ecosystem, experts really need to be viewed as such for voters to trust them with their stake. Furthermore, this creates an incentive to become knowledgable about the ecosystem - since the likelihood of reaping participation rewards are significantly higher as an expert than as a voter. 

Still, an expert could socially engineer a large set of voters to trust him/her and deviate from his/her "promises" if they are more knowledgeable, but in the long-run, such a tactic may not work as the likelihood of being caught is large. Indeed, it would be more rational to maintain a dominant position as a "more than average" knowledgeable person and reap consistent reweards, than to potentially reap high rewards once.

Interestingly enough, experts are also free to delegate their accumulated votes to other experts. This means that there are situations were a subset of the total set of experts end up with significant stake, at which point they may be incentivized to deviate to greater degree. 

### Committee

The committee is crucial for the Cardano governance system. Think of the committee as being analagous to miners in a generic blockchain consensus system as both miners and the committee makes sure the system satisfies the liveness criteria of the protocol.

There is a difference however. In Cardano, there are up to `k` randomly chosen committee members, but there is only `1` randomly selected block author per round in the blockchain consensus layers. Their fundamental role is not to produce blocks, but rather to tally the votes committed by experts and voters and guarantee that no other committee members lies. Consequently, they are crucial for maintaining Cardano's governance system's "verifiability" concern.

That being said, the consensus algorithm used to agree on a particular tally amongst the `k` committee members differs from that of agreeing on a particular block.

### Evaluating the 

he Cardano governance period is crucial to a funding round. It consists of three epochs: 

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
are in stead voters which are randomly chosen with some probability, where the larger the stake in a voting round deposited by a voter, the greater the probability of being chosen. Currently, the number `k` is defined at 500, which means there would be about 500 committee members per funding round. This does not mean much without context, however. The last funding round had around 250,000 voters participating, so `k` is therefore significantly smaller than `n` where `n` represents number of votrers.

It is also worthwhile mentiuoning that once a randomly chosen committee member has been randomly chosen to participate in the committee, the voter himself must confirm their position on the committee with a special registration transaction.


### Cryptographic primitives

The primitives used in governance are highlighted [here](../Cryptography.md)

### Answers to the questions

2 things we liked about the Cardano Blockchain Governance system:
- Liquid democracy (the ability to delegate votes to an expert, and for experts to delegate their votes further as well)
- The commit-reveal mechanism which allows the committee to generate a random seed for the next round of voting

2 things we disliked about the Cardano Blockchain
- The lack of a mechanism to prevent our potential attack vector
- The fact that voting power is proportional to stake.