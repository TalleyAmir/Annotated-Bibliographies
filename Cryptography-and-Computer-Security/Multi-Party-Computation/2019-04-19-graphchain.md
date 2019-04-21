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

Incentives for mining are allocated based on the prize of a transaction.

### Depletion Strategy

Draining the reward tactfully to maintain the incentive to mine.

## Security

### Conflicts and Consensus

Double spending; submarine attack resistence (i.e. convergence); liveness via leading edge preference.

### Minting and Inflation

...

## Performance

Implementation; runtime; simulator experiments.

## Citation

Boyen, Xavier. Carr, Christopher. Haines, Thomas. Graphchain: a Blockchain-Free Scalable Decentralised Ledger. 21-33. 10.1145/3205230.3205235. (2018), [https://dl.acm.org/citation.cfm?id=3205235](https://dl.acm.org/citation.cfm?id=3205235)
