# Cryptography, Economics and Blockchains Midterm: Cardano

---
##  Introduction

[Cardano](https://cardano.org) is a third generation "proof-of-stake blockchain platform: the first to be founded on 
peer-reviewed research and developed through evidence-based methods"[^1]. It defines itself as "a financial system 
that accepts its social nature" and a financial stack for the developing/unbanked world.

The whitepaper can be found at https://whitepaper.io/whitepapers/cardano.

### Core offerings
What are the core offerings of this blockchain/project?

- Academic research: formal methods to achieve strong guarantees
- Separation of concerns: separation of settlement and computation layers
  - Cardano Settlement Layer (CSL):
    - Scripting
      - **Simon** - domain-specific language on the settlement layer, focusing solely on financial transactions. 
        Enhanced security and correctness through proofs.
      - **Plutus** - general purpose smart contract language and special purpose DSL for interoperability
    - Sidechains: KMZ sidechains, allowing non-interactive movement of funds from CSL to CCL or any other chain 
      supporting KMZ protocol
    - Multiple Signature Schemes: Security durability vs preferred schemes within certain contexts 
    - Scalability:
      - Consensus algorithm permits decentralised way to elect quorum of trusted consensus nodes per epoch
      - Multiple quorums elected concurrently and transactions partitioned to quorums
      - Similar methods for network propagation and sharding of chain data into unique partitions
    - Multiple assets in same ledger (User Issued Assets (UIAs))
  - Cardano Computation Layer (CCL):
    - Formalised EVM with security risks minimised
    - Solidity for low assurance applications
    - Plutus for higher assurance applications requiring formal verification
    - Possible to create specialised token held by regulated entities, thereby creating a permissioned ledger. 
      Non-attributed transactions could therefore be blacklisted.
    - Hardware Security Modules & Sealed Glass Proofs: sensitive information can be warehoused in hardware enclaves 
      of trusted attestors, enabling fact verification without exposure of underlying identity
- Decentralised funding mechanism
- Regulation
  - Strong guarantees of fraud-free commerce through smart contracts and settlement layer
  - HSMs to provide identity with strong PII protection
  - Regulation DAO which interacts with smart contracts to add mutability, consumer protection and arbitration
  - Enriching of transactions through optional metadata
    - Labeling of transactions and financial activity (e.g. tax accounting)
    - Special addresses that can include hashes and encrypted fields
  - Authentication and Compliance
    - Sealed Glass Proofs to submit compliance information (e.g. KYC) to verifier who is forced to comply with policies 
    - it was submitted under, protecting the information from leaks
  - Marketplace DAOs
    - smart contract enforced market place structures which codify contract law and business best practices
- Delegated Proof of Stake as a consensus mechanism

### Usage

The native token can be used as digital currency on the platform for fee payment, deposits and receiving rewards. 

Users can earn a share of block rewards by (delegated) staking of tokens, which are used to secure the network. 
Users can also interact with decentralized apps (DApps) through a recent release of general-purpose smart contract 
functionality[^2]. Finally, users can also vote on project funding and network improvements, with votes weighted by 
stake. 

### Differentiation
The differentiating factors of the project are as follows:

- It takes a scientific, research-based and peer-reviewed approach 
- separation of settlement and computation layers for increased flexibility 
- eUTXO model advantages (todo)
  - accounting model: all state stored as outputs of previous transaction
  - additional metadata stored in separate output
- multi-assets: transacting with custom tokens natively

### Team members: 
Aaryamann, Adam, Anton, Daan, Mattia, Frank

## Outline

1. [Cryptography](Cryptography.md)
2. [Economics](Economics.md)
3. [Governance](Governance.md)
4. [Blockchain Structure](BlockchainStructure.md)
5. [Blockchain Guarantees](BlockchainGuarantees.md)
6. [Threat Models and Security](ThreatModelsAndSecurity.md)
7. [Conclusion](Conclusion.md)
8. [Appendix](Appendix.md)
9. [Additional Links](Links.md)

---
### Footnotes
[^1]: https://cardano.org
[^2]: [Guogen Era](https://roadmap.cardano.org/en/goguen) (Sep 2021) using Haskell, Simon, Plutus, Marlowe languages
[^?]: Additional source: https://www.cryptoeq.io/corereports/cardano