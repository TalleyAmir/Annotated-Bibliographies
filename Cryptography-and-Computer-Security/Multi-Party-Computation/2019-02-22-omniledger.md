# Summary of "OmniLedger: A Secure, Scale-Out, Decentralized Ledger via Sharding"

## Relevant Background

Many works prior to OmniLedger aim to build a distributed ledger; however, these prior works exhibit a trade-off between scalability, security, and decentralization.

## Main Contribution

OmniLedger proposes multiple tools that are then used to build a scalable, decentralized ledger with various security guarantees. Several of these tools build upon previous schemes for secure multi-party computation (RandHound) and byzantine consensus (ByzCoin), while others are novel constructions (Atomix).

## Tools

### RandHound

OmniLedger achieves scalability by using a randomized algorithm for selecting a representative committee of transaction block validators. This algorithm is called RandHound, and was proposed in a paper titled "Scalable Bias-Resistant Distributed Randomness" in 2017. RandHound uses the pigeonhole principle to ensure that at least one honest party contributes to the multi-party computation, guaranteeing that the output is necessarily random and cannot be biased. Cryptographic sortition (see Algorand review) is used to select a single validator to play the role of leader and invoke the RandHound algorithm. The output of the coin-toss (with its correctness proof) is then broadcast to all parties and the random bits are used to assign individual parties to shards. 

The security of this shard-assignment algorithm relies on both the security of RandHound and Algorand's cryptographic sortition. Randhound guarantees that the adversary cannot bias the output randomness and cryptographic sortition guarantees that only one leader is elected verifiably. If the leader is corrupted, then the only risk is that the adversary withholds the coin-toss. In this scenario, the protocol times-out after a fixed period, at which point the protocol is re-run from the start. The expected number of times the protocol will need to be re-run until an honest leader is elected is probabilistically bounded.

RandHound was selected to be used for the purpose of random coin generation because it is both scalable and distributed, and has adequate security guarantees. Moreover, it has open-source code and was therefore able to be used for testing OmniLedger's performance in implementation.

### ByzCoinX

ByzCoinX is closely modelled after ByzCoin's (2016) Byzantine fault-tolerant consensus protocol. The additions made to this protocol by OmniLedger increase the protocol's robustness to denial of service attacks. In addition, it increases performance by resolving transaction conflicts in real time to allow different shards to parallelize computation.

### Atomix

Atomix is a Byzantine Shard Atomic Commit protocol that enables OmniLedger to perform and commit transactions across multiple shards (as is likely the case for most transactions in practice). Furthermore, it prevents double-spending and ensures that unspent currency from failed transactions are not forever locked. It does this using a three-step protocol in the UTXO (Unspent Transaction Output) model that consists of:

+ Initialize: A client creates a cross-shard transaction by gossiping the request to a subset of "input shards."
+ Lock: For each input shard, the input shard leader verifies the transaction. If successful, the leader commits it to the shard's ledger, issues a proof-of-acceptance, and marks the UTXOs as spent. Otherwise, it issues a proof-of-rejection.
+ Unlock: There are two cases. Either the transaction was successful (which happens if _and only if_ every input shard leader issued an acceptance of the transaction) or it was not. If the transaction succeeded, then the client commits the transaction to some "output shards." Otherwise, the client aborts the transaction and marks the UTXOs as spendable.

## Throughput Optimizations

### Optional trust-but-verify validation

### Parallelization

### State blocks

## Performance

...

## Citation

Kokoris-Kogias, E., Jovanovic, P., Gasser, L., Gailly, N., Syta, E., Ford, B: OmniLedger: A Secure, Scale-Out, Decentralized Ledger via Sharding. In 2018 IEEE Symposium on Security and Privacy (S&P), pages 19–34. (2018), [https://eprint.iacr.org/2017/406.pdf](https://eprint.iacr.org/2017/406.pdf)
