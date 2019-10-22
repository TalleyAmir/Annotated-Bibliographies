# Time and Space Optimal Counting in Population Protocols


## Citation

James Aspnes, Joffroy Beauquier, Janna Burman, and Devan Sohier. "Time and space optimal counting in population protocols." In Proc. of International Conference on Principles of Distributed Systems, pages 13:1–13:17, 2016. [http://drops.dagstuhl.de/opus/frontdoor.php?source_opus=7082](http://drops.dagstuhl.de/opus/frontdoor.php?source_opus=7082).

## Relevant Background

Population protocols are used to simulate ad hoc networks of limited-memory mobile devices. Though most of the devices, called agents, in the network have limited memory storage, often times a "base station" -- a single agent with greater computational power than the rest of the agents -- is introduced.

## Main Contribution

This paper gives and proves the optimality of a counting algorithm that uses two states per agent and a base station and converges in O(n log(n)) parallel time (i.e. O(n^2 log(n)) interactions).

## Description of Algorithm

All agents are anonymous except the base station, i.e. there is no way to distinguish between two agents with the same state. The two states that are used in this algorithm are denoted by bits 0 and 1. Agents are initialized to either of these bits at random; the starting state of the agents does not affect the correctness of the algorithm.

The algorithm runs in phases. In the first phase, ...

The authors prove that the expected number of phases that need to be run in order to count the number of agents is constant (8 or 9 depending on the initial configuration of agent states).

## Analysis and Future Work
