# Summary of "Graphchain: A Blockchain-Free Scalable Decentralized Ledger"

## Relevant Background

The primary appeal of digital cryptocurrencies is that they allow us to achieve publicly verifiable and non-repudiable transactions without a centralized authority validating identities and transactions. However, the main mechanism for achieving this kind of decentralization to date has been blockchain. Though blockchain contains the desired properties for implementing cryptocurrencies, the transaction latency is insurmountable. Furthermore, 51% (and fewer) attacks can be used to exploit blockchains due to mining pools.

## Main Contribution

Graphchain is a blockchain-free scalable decentralized ledger that generates blocks and adds them to the chain via a rational incentive mechanism. The pattern in which blocks are cross-verified results in a directed graph that is long and thin, minimizing transaction latency and preventing submarine attacks.

## Tools

The Graphchain is built using an incentive mechanism that encourages transactions to verify a few parent transactions, prioritizing transactions that are more recent and of higher value. The system guarantees _strong convergence_, ensuring that transactions are heavily interwoven and making the graphchain as immutable as blockchain.

### Transactional Framework

A Graphchain transaction _x_ = <_t_, _p_, _f_, _m_, _s_> consists of a payment (or contract) _t_, an affirmation of at least one parent transaction _p_, a fee _f_, a mint amount _m_, and a puzzle solution _s_. A set of transactions can be represented as a Transactional Partially Ordered Set, or as denoted in this paper, a T-POSET. The _weight_ of a transaction _x_ is the sum of the proof-of-work difficulties of _x_ and all of the descendants of _x_ (every transaction _y_ that whose proof encompasses that of _x_, as well). Similarly, the _height_ of _x_ is the sum of the proof-of-work difficulties of _x_ and all of the ancestors of _x_.

### Fees and Rewards

For each transaction _x_, _f_ must be positive to offset the cost of verification. Implementations can specify a minimum cost, but if they do not, the market drives the cost of these fees. This fee drives the prize of a transaction, which corresponds to the sum of the fees of _x_ and all of its ancestors that have not yet been claimed by miners. This incentivizes verifying newer transactions faster because these transactions have not yet had any of their fees depleted.

### Depletion Strategy

Graphchain uses a tactful draining strategy to deplete the reward from transactions in such a way that maintains the incentive to mine newer transactions. By redeeming the fees from older transactions first, verifiers are more inclined to verify newer transactions.

## Security

Though conflicts are mostly avoided through prompt validation of new transactions, conflicts can still occur if a malicious user tries to double spend a coin, or spend coins with greater value than the user possesses. In the case of transaction conflicts, the Graphchain favors the T-POSET with the tallest well-formed transaction.

In order to reverse an honest transaction, an adversary must generate a new transaction whose cumulative proof of work is greater than that of the original transaction. When a transaction is "burried beneath" sufficiently many descendant transactions, this becomes infeasible or unprofitable. Thus the _weight_ of a transaction directly corresponds to its level of security. 

Graphchain assumes a rational model where the majority of miners act honestly except when acting selfishly benefits them. Further, it assumes that at least half of the miners are uncorrupted. The optimal strategy for creating a new transaction in this graph network under these assumptions is to select parent transactions with no other descendants (this is called the leading edge preference) because these transactions have the highest prize value; if a transaction has no descendants, none of its fees have been collected yet. This property is termed _convergence_. In particular, after a certain amount of time, all transactions verified up until some fixed point in time will share a common descendant. Moreover, _strong convergence_ dictates that for some initial T-POSET _P_, there will eventually be a transaction that is a descendant of all transactions in _P_. This property allows us to claim that submarine attacks are unachievable.

## Performance

The authors implement skeleton algorithms for this design in Rust and test that it exhibits the correct behavior and expected runtime. The authors observed that even if the parents of transactions are chosen randomly (perhaps subject to constraints? But they do not specify), the graph converges very quickly. In fact, when run a single machine (i7-4770 CPU), Graphchain achieves the same throughput as Bitcoin.

<p align="center">
  <img width="700" src="https://github.com/TalleyAmir/Annotated-Bibliographies/blob/master/Cryptography-and-Computer-Security/Multi-Party-Computation/images/graphchain.png?raw=true"></br>
  Image taken from Graphchain paper, see citation below.
</p>

## Citation

Boyen, Xavier. Carr, Christopher. Haines, Thomas. Graphchain: a Blockchain-Free Scalable Decentralised Ledger. 21-33. 10.1145/3205230.3205235. (2018), [https://dl.acm.org/citation.cfm?id=3205235](https://dl.acm.org/citation.cfm?id=3205235)
