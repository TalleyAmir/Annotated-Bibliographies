# Summary & Review of "Leakage-Resilient Coin Tossing"

## Relevant Background

Leakage-resilient coin tossing is an important cryptographic tool that allows a group of entities to jointly compute and agree upon a fixed amount of randomness. Such randomness can then be used to execute locally the output of some non-deterministic function, allowing each party to obtain consistent results in executing some distributed algorithm.

## Main Contribution

This paper offers a protocol for computing unbiased coin tossing of _m_ fair coins among _n_ parties in _O(1)_ rounds, accounting for a fraction of each party's local state being leaked to an adaptive adversary.

## Key Concepts

### Leakage-Resilience

### Verifiable Computation

## Tools

### Oblivious verifiable secret sharing

Secret sharing (SS) is a cryptographic primitive that allows a dealer to generate shares of a secret message and distribute those shares to a group of parties such that the original secret can be constructed if, and only if, some threshold number of shares are pooled together. Verifiable secret sharing (VSS) is a type of SS wherein if the dealer is dishonest, then the honest parties can reject the dealer's shares, or otherwise the dealer is committed to some secret that the honest parties can later reconstruct from their shares.

The construction itself extends Shamir secret sharing. Two constructions are offered: one weakly leakage-resilient and one strongly leakage-resilient. The weaker version is sufficient to achieve the leakage-resilience properties sought after in the coin tossing scheme, but the stronger version naturally follows and is "of independent interest," according to the authors.

Properties:

 *
 *
 *

### Disjoint committee election

The committee election scheme offered by this paper extends the Feige "lightest bin" protocol. It is used to partition the _n_ parties into _m_ committees such that the size of each committee is within specified limits and the expected number of corrupted parties in each committee is bounded by a fixed fraction.

This partitioning is done by running Feige's lightest bin protocol _n_ times, in series. In each round, each party broadcasts a random number between 1 and _n/k_ and the parties in the least-value bin are elected to the committee in that round. This is done _m_ times, and for each subsequent round, if a party was previously elected to a committee, they are removed from all subsequent committees to which they are elected.

Properties:

 * Disjoint committees
 * Bounded size of committees
 * Bounded fraction of corrupted parties per committee

### Robust multi-source extractor

Properties:

 *
 *
 *

## Construction

## Citation

Boyle, E., Goldwasser, S., Kalai, Y.T.: Leakage-Resilient Coin Tossing. In: Peleg, D. (ed.) DISC 2011. LNCS, vol. 6950, pp. 181–196. Springer, Heidelberg (2011), [http://eprint.iacr.org/2011/291](http://eprint.iacr.org/2011/291)
