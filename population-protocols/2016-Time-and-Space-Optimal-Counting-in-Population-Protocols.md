# Time and Space Optimal Counting in Population Protocols


## Citation

James Aspnes, Joffroy Beauquier, Janna Burman, and Devan Sohier. "Time and space optimal counting in population protocols." In Proc. of International Conference on Principles of Distributed Systems, pages 13:1–13:17, 2016. [http://drops.dagstuhl.de/opus/frontdoor.php?source_opus=7082](http://drops.dagstuhl.de/opus/frontdoor.php?source_opus=7082).

## Relevant Background

Population protocols are used to simulate ad hoc networks of limited-memory mobile devices. Though most of the devices, called agents, in the network have limited memory storage, often times a "base station" -- a single agent with greater computational power than the rest of the agents -- is introduced.

## Main Contribution

This paper gives and proves the optimality of an algorithm that counts the number of constituents in the population. The algorithm uses two states per agent (which is the fewest number possible) and a base station. The algorithm converges in _O_(_n log(n)_) parallel time (i.e. _O_(_n^2 log(n)_) interactions) and this is proven to be optimal, as well.

## Description of Algorithm

All agents are anonymous except the base station, i.e. there is no way to distinguish between two agents with the same state. The two states that are used in this algorithm are denoted by bits 0 and 1. Agents are initialized to either of these bits at random; the starting state of the agents does not affect the correctness of the algorithm.

The base station (BST) tracks an approximation of the number of agents with bit 0 (c0) and with bit 1 (c1). The algorithm runs in phases, each of which consists of the same series of steps. The only interactions that matter are ones that involve the BST because the BST performs the actual computation of counting the total number of agents. Each phase is either considered a 0-phase or a 1-phase and the protocol starts in the 0-phase. In the _b_-phase, any time an agent with bit _b_ interacts with the BST, the BST flips the agent's bit from _b_ to 1-_b_. If the agent had bit 1-_b_, the BST increments a counter that tracks how many 1-_b_ bits it has seen this round. If this counter exceeds 6 _cb log(cb)_, then the previous approximation must have been incorrect because the likelihood that the BST interacts with 6 _cb log(cb)_ agents in state 1-_b_ is 

The authors prove that the expected number of phases that need to be run in order to count the number of agents is bounded by a constant (8 or 9 depending on the initial configuration of agent states).

## Analysis and Future Work

