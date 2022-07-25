<!-- .slide: data-background-color="#8D3AED" -->

# Threat Models and Security

<widget-text style="padding: 0 3em 0 3em">
---

### Byzantine Generals Problem
- PoS empowers uncoordinated "generals" to agree
- Preset algorithm decides which is leader
- All other "generals" accept leader and accept block it creates

<widget-text style="padding: 0 3em 0 3em">
---

### 51% Attack
- No blockchain can prevent a 51% attack
- Also, BGP hijack (routing layer) can easily enable that - no protection mentioned

<widget-text style="...">
---

### Sybil Attack
Operator controlling large amount of stake pools could control entire network

- Prevented in Cardano via "pledging" 
- Operators entitled to bonus reward by pledging portion of own funds 
- Incentivizes operators to have higher pledge, discouraging from creating multiple stake pools

<widget-text style="...">
---

### Double spending attack
 - Once transaction confirmed by honest player, all other honest players (from that point on) will never disagree on 
   transaction
 - Thus impossible to bring system to state where confirmed transaction invalidated

<widget-text style="...">
---

### Grinding attacks
- Stake grinding attacks: adversary tries to influence slot leader election process to improve chances of selection
- Cardano uses 'coin tossing' protocol, proven to generate unbiased uniform randomness to elect new block producer

<widget-text style="...">
---

### Transaction denial attacks (censorship)
- Transaction denial attack: adversary prevents certain transaction from becoming confirmed
- Liveness ensures that it will be eventually confirmed, provided transaction attempted to be inserted for sufficient number of slots by network

<widget-text style="...">
---

### Desynchronization attacks
- Desynchronization attack: shareholder behaves honestly but incapable of synchronizing correctly with network 
- No guarantees of liveness and persistence provided for desynchronized parties
- Network secured as long as parties with < 50% of stake get desynchronized 
- If > 50% parties desynchronized, protocol can fail

<widget-text style="...">
---

### Bribery attacks
- Bribery attacks: adversary deliberately pays block producers to work on specific blocks/forks, aiming at 
generating fork benefiting adversary 
- Malicious slot leaders who agree risk foregoing potential profit earned from behaving honestly 
- Loss from currency devaluation can easily offset additional profits made by participating in attack

<widget-text style="...">
---

### Selfish Mining
- Selfish mining attack: attacker withholds blocks, releasing strategically, attempting to drop honestly 
  generated blocks 
- Prevented by slot mechanism: 
  - elected slot leader able to make one new block
  - If it withholds block, next elected slot leader will produce next block

<widget-text style="...">
---

### Nothing At Stake Attack
- Nothing-at-stake: theoretical security issue in PoS in which validators have financial incentive to build on every 
  fork of chain
- Prevented by randomness of next block creator

<widget-text style="...">
---

<!-- .slide: data-background-color="#8D3AED" -->

## Secure Transactions
- Deterministic Finality: all transactions guaranteed to exist on ledger after at least 36 hours passed
- eUTXO: prevents double spending, secured by chain of signatures

<widget-text style="...">
---

## Two Things we liked
- Upgradability of cryptographic primitives
- Stake pools securing PoS consensus protocol

<widget-text style="...">
---

## Two things we disliked
- The ADA Total supply very high compared to Bitcoin, which could lead to less fees being paid out to Stake Pool 
  Operators, which in turn, could disincentivize them from participating in the network
- Most security proofs argued for on theoretical basis, unclear to which extent actual implementation satisfies theory
