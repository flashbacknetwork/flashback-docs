# Minimal Requirements

## General Configuration

Flashback proposes a genesis with a Proof-of-Stake (PoS) consensus mechanism. The minimal hardware requirements for running a validator node would be significantly less demanding than those for mining in a Proof-of-Work (PoW) system or current Ethereum chain. Here’s what you would likely need:

### Minimal Hardware Requirements for a PoS Validator Node

As Flashback inherits from the Ethereum specifications, the network can support light, full, and archive nodes. Flashback does not have the history of Ethereum and can reduce certain specifications. The minimal hardware requirements must then evolve with the growth of the Flashback ecosystem. &#x20;

| Category          | Light Node              | Full Node                | Archive Node            |
| ----------------- | ----------------------- | ------------------------ | ----------------------- |
| CPU               | 2 cores - 4 threads     | 4 cores - 8 threads      | 8 cores - 16 threads    |
| RAM               | 2 GB                    | 8 GB                     | 32 GB                   |
| Storage           | 50 GB (SSD recommended) | 500 GB (SSD recommended) | 2 TB (NVMe recommended) |
| Network Bandwidth | 10 Mbps                 | 25 Mbps                  | 100 Mbps                |

### Additional Considerations

* **Backup and Security**: Since validators must keep their private keys secure, consider using hardware security modules (HSMs) or secure offline storage (cold wallets) for private keys.
* **Redundancy**: For those seeking to operate a highly available node, consider setting up failover systems or backup internet connections to ensure continuous operation
