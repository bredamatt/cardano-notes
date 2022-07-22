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

These definitions will be discussed loosely as we evalaute the different components that constitute the Cardano governance system. But first, let us define  why we need a governance system.

## Purpose

For any ecosystem to have a sustainable future, it is necessary to govern a system's evolution. Yet the key point, is to figure out in which direction the ecosystem is evolving (to something better, or worse?).

It is quite common to state that the purpose of a governance system is to maximize the utility of its participants. It follows that we need to know what the utility function of a participant in the community would be, but for now we can simply state it is about a positive evolution of the Cardano ecosystem. An example of this would be when meaningful projects and use-cases are implemented on the Cardano blockchain. 

In general, governance problems arise whenever it becomes rational for an individual actor to game / play the system for his/her own benefit at the expense of the common good of the community. Hence, we could say that a particular governance system is good only as far as it makes it rational for system participants to act in the interest of the common good. In other words, a well-designed governance mechanism would also be capable of incentivizing agents, or at least indirectly making them act in the interest of the common good, even when it may initially appear rationally not to.

The above points are important to take into consideration when assessing the Cardano governance mechanism with respect to the Blockchain Governance definitions below.

In general, however, we can say that a governance system is focused on maximizing the utility of its community members by guaranteeing that the 7 definitions are satisfied.

## Blockchain Governance definitions

### 1. Suffrage

*"The right to participate
in decision making procedures."*

Rights may be provided in various ways:

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
 
As we learned from the collective decision making games in class, even if on the average it is rational to contribute to common good, there are occassions where it is more rational to deviate. Here, rationality implies making a decision that maximizes the decision maker's utilit y rather than that of the collective. This is also important to take into consideration, when considering the extent to which the good of the community has a positive impact on the individual's utility. In a Blockchain scenario, the most common binder between an individual actor, and the community itself, is its underlying token. Hence, any person deciding to join the commuinity may have good intentions, but may nevertheless face a scenario where it is more beneficial to deviate, such as for example disrupting a positive project, when a short position on the tokens value exists. ...But, because stake in the system is relative to the amount of ADA tokens a particular community member holds, it would arguably make the most sense that there are financial incentives at play, and that these financial incentives prevent adversarial behavior. 

### Is the treasury system implemented?

A core question we tried to answer was the extent to which the treasury system is implemented. According to the [Treasury system paper](https://eprint.iacr.org/2018/435.pdf), Cardano's Voltaire release will contain its implementation. Currently, however, there exists a publicly available governance interface, namely [Project Catalyst](https://projectcatalyst.org/), an online platform where community members can learn about how to come up with their own proposals, vote, and assess proposal accordingly. This looks very similar to the ideas discussed in the academic paper.

It was important for us to see how easy it was to sign up to, and participate in the Cardano Community. We were surprised that there was not a perfect mapping between the paper and Catalyst. However, we signed up to Project Catalyst as a standard user so we could evaluate the governance system's practicalities in more detail. Signing up was quite straightforward, as we just signed up with an email address.

Unfortunately, we were unable to propose a new project because the deadline had passed, but there was a well-defined interface for doing so, and we quickly found out the different stages/rounds from project ideation to funding a particular "governance round" consists of. It is also worthwhile mentioning that there is a term called "Campaigns" which represents group of proposals with a common theme. Proposals must belong to a particular campaign accordingly.

The rounds defined on Catalyst's platform were:

- Proposal
- Review
- Finalize
- Assessment
- Assess QA
- Governance (AKA voting phase)

The academic paper, however, focuses on Governance. For the sake of brevity, we will concentrate primarily on this paper from here onwards, but it is necessary to briefly cover what the different periods represent.

#### Catalyst periods

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

Inactive proposals are eventually archived. The definition of inactive is unclear.

### Treasury funding

As mentioned, Cardano uses a treasury-model for collective decision making purposes. This means that the community decides via some process, how to use the funds in the treasury primarily. The exact way this happens in Voltaire will become more clear with time.

Even if Voltaire will be the first release of the implementation of Cardano's governance paper, it does not necessarily mean there exists no treasury, and collective decision making today. In fact, the treasury is already live, but we are uncertain as to the extent to which it is implemented  according to the security principles outlined in the theoretical/academic paper.

According to Catalyst, Cardano's treasury system is on Funding round 9 (usually listed as FUND9). The data surrounding the treasury, and its overall funding history, is relatively transparent, but not necessarily easy to understand in relation to the documentation that exists. The data is generally shared through a shared Google Doc, which is publicly readable, but terminology is defined across various information sources making it not that straightforward to understand what the numbers mean. See for example: ["treasury-exceeded-900-million-ada-held"](https://cardanofeed.com/cardano-treasury-exceeded-900-million-ada-held-here-s-what-they-spend-it-on-84369.html).

As mentioned, Cardano uses a treasury system to govern the evolution of the protocol, however Cardano was not the first platform to do so (the Dash governance system invented the treasury model in the blockchain space apparently). In a treasury system, the collective decides upon where funding is allocated. That being said, the funds have to arrive from somewhere, hence there exists a set of funding mechanisms to make the governance system sustainable.

#### Funding mechanisms

In the Cardano governance system, the treasury is funded in three different ways:

1. when new blocks are minted, a proportion of the rewards goes to the treasury
2. miners' rewards are taxed, and the tax is collected by the treasury
3. donations, or charity are also possible venues of funding proposals

It has been shown (see the Treasury link above) that the treasury appears to be growing in value. It is not clearly documented who owns the private keys for the treasury accounts, however.

### Voltaire in detail

First and foremost Voltaire is designed to utilize a *fuzzy voting system*. Such a voting system generally 

Voltaire, and the Cardano governance system is focused on defining consensus not necessarily on the terms of "unanimous agreement", but in stead on a set of metrics that indicate the extent to which voters vote according to the priorities of the community. They thereafter use the set of metrics estimated per voting phase to provide feedback to voters, to satisfy both the verifiability definition above. In this way, voters can be re-assured that their vote is their "true" vote.

Additionally, there are other benefits related to distributing such metrics, as the information provided by the feedback loop gives community members the ability to sense the extent to which they may need to adjust their preferences to align with the community. Although it is arguable that such a metric-based approach can potentially lead to a skewed vote outcome, the Cardano research team refers to other academic work focused on the nature of consensus in large groups as representative of the benefits of such an approach. Furthermore, the purpose behind this design decision 

### Voters
These are community members who decides to vote on the projects proposed in a particular funding round. They do this by depositing an amount of ADA as a security deposit. The more they deposit, the more voting power they have. Because voting power determines which proposals win, taking a risk in a particular voting round by depositing ADA, leads to "skin-in-the-game", and therefore also accountability (if you lose by making a poor voting decision, you lose your ADA).

Still, it is possible that an inexperienced voter with large degree of stake disrupts the funding round by accidentally, or deliberately voting for a suboptimal proposal from a Pareto efficiency perspective. Yet, the extent to which voters with large stake would not want the best result for the collective is questionable since a bad outcome is something they themselves would be held accountable for. Additionally, there are opportunities to delegate stake to a funding round "expert", and this delegation mechanism is particularly valuable to give unknowledgable, but what may potentially be disruptive voters (by accident in this case) the ability to reach Pareto optimality to a greater extent.

In summary, it seems that the future Cardano governance system aims to implement *liquid democracy* to partially solve the problem of votes being passed **accidentally** to Pareto inefficient proposals. Because it is a choice whether to delegate, or not, there are *no guarantees* of Pareto efficiency as a consequence.

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

There is a difference however. In Cardano, there are up to `k` randomly chosen committee members, but there is only `1` randomly selected block author per round in the blockchain consensus layers. The committee members in the treasury system is not to produce blocks, but rather to tally the votes committed by experts and voters and guarantee that no other committee members lies. Consequently, they are crucial for maintaining Cardano's governance system's "verifiability" and "sustainability" concerns.

That being said, the consensus algorithm used to agree on a particular tally amongst the `k` committee members differs from that of agreeing on a particular block, and is actually rather involved.

### Evaluating the behavior of committee members

As mentioned, the more interesting aspects of the committee members behavior is best analysed during the governance period. This period consists of three different epochs:

1. Pre-voting/preparation stage,
2. Voting stage, and
3. Post-voting stage

#### Pre-voting

During the pre-voting stage, two things happen:

- projects are proposed as described above, and
- voters and experts register by submitting special transactions on the blockchain and locking up some stake
  
#### Voting 

During the voting epoch there are three main things for the participants to partake in:

- committe selection stage,
- distributed key setup stage, 
- ballot casting stage

#### Post-voting 

The post-voting stage consists of a:

- tally stage (when votes are counted)
- execution stage

### Cryptographic primitives

The primitives used in governance are highlighted [here](../Cryptography.md).

