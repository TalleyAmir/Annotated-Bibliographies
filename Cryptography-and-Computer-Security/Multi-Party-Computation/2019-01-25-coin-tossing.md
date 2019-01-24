# Summary & Review of "Leakage-Resilient Coin Tossing"

## Relevant Background

Leakage-resilient coin tossing is an important cryptographic tool that allows a group of entities to jointly compute and agree upon a fixed amount of randomness. Such randomness can then be used to execute locally the output of some non-deterministic function, allowing each party to obtain the same result.

## Main Contributions

This paper offers a distributed algorithm for computing unbiased coin tossing of _m_ fair coins among _n_ parties in _O(1)_ rounds, accounting for a fraction of each party's local state being leaked to an adaptive adversary.

## Tools

### Oblivious verifiable secret sharing

Secret sharing (SS) is a cryptographic primitive that allows a dealer to generate shares of a secret message and distribute those shares to a group of parties such that the original secret can be constructed if, and only if, some threshold number of shares are pooled together. Verifiable secret sharing (VSS) is a type of SS wherein if the dealer is dishonest, then the honest parties can reject the dealer's shares, or otherwise the dealer is committed to some secret that the honest parties can later reconstruct from their shares.

### Disjoint committee election
### Robust multi-source extractor

## Important Definitions

## Construction
