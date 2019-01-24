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

A robust multi-source extractor is a function that takes input from several independent sources and generates from these inputs a string that is negligibly different from uniformly distributed. In these circumstances, robustness means that even if some of the sources come from corrupted parties, the output string will still appear indistinguishable from uniform so long as the inputs of the corrupted parties are independent of those of the honest parties.

The construction used in this paper was taken from the 2006 work of Kamp, Rao, Vadhan, and Zuckerman.

## Assumptions

 * Communication channels between pairs of parties are secure.
 * Events are synchronous.
 * Up to 1/3 of parties may be corrupt.
 * The adversary is adaptive, computationally unbounded, and can make _leakage queries_, which together imply that the resulting construction is information theoretically secure.

## Construction

The coin toss is performed in four steps, followed by a single computation performed locally by each of the parties.

 1. Run the Feige lightest bin protocol to select a primary committee of size _w_.
 2. Run the disjoint committee election protocol to partition the remaining parties into _w_ secondary committees.
 3. Each member of the primary committee selects a random value and verifiably secret shares the value to its corresponding secondary committee.
 4. Secondary committees reconstruct the random value and each party in the committee broadcasts the value to all other parties. If the dealer was rejcted, 0 is broadcast instead.
 5. Locally, each party takes the most common value _r_ received from each secondary committee and computes _R_ = EXT({_r_}), where EXT is a robust multi-source extractor whose input is the set of all reconstructed _r_. Each party outputs random coin flip _R_.

## Citation

Boyle, E., Goldwasser, S., Kalai, Y.T.: Leakage-Resilient Coin Tossing. In: Peleg, D. (ed.) DISC 2011. LNCS, vol. 6950, pp. 181–196. Springer, Heidelberg (2011), [http://eprint.iacr.org/2011/291](http://eprint.iacr.org/2011/291)
