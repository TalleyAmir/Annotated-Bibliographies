# Summary of "Graphchain: A Blockchain-Free Scalable Decentralized Ledger"

## Relevant Background

The primary appeal of digital cryptocurrencies is that they allow us to achieve publicly verifiable and non-repudiable transactions without a centralized authority validating identities and transactions. However, the main mechanism for achieving this kind of decentralization to date has been blockchain. Though blockchain contains the desired properties for implementing cryptocurrencies, the transaction latency is insurmountable. Furthermore, 51% (and fewer) attacks can be used to exploit blockchains due to mining pools.

## Main Contribution

Graphchain is a blockchain-free scalable decentralized ledger that generates blocks and adds them to the chain via a rational incentive mechanism. The pattern in which blocks are cross-verified results in a directed graph that is long and thin, minimizing transaction latency and preventing submarine attacks.

## Tools

### Transactional Framework

Transactional partially ordered set, or T-POSET; height and weight of a transaction.

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
