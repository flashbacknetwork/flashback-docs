# Hardware Requirements

## Participate in the Staking only

Flashback proposes a genesis with a Proof-of-Stake (PoS) consensus mechanism. The minimal hardware requirements for running a validator node would be significantly less demanding than those for mining in a Proof-of-Work (PoW) system or current Ethereum chain. Here’s what you would likely need:

### Minimal Hardware Requirements for a PoS Validator Node

1. **CPU**:
   * A multi-core processor, such as a modern dual-core or quad-core CPU (e.g., Intel i5 or AMD Ryzen 5), is recommended. These provide sufficient power for the processing tasks a PoS validator requires.
2. **RAM**:
   * **4GB - 8GB** of RAM should be sufficient. Running a full node on PoS requires less memory since the focus is on validating transactions rather than solving complex cryptographic puzzles.
3. **Storage**:
   * **500GB - 1TB SSD**. Ethereum nodes require fast access to the blockchain data, and an SSD is crucial for this. The storage should be sufficient to store the blockchain data as it grows over time. A solid-state drive (SSD) is preferred over a traditional hard drive (HDD) due to its faster read/write speeds, essential for maintaining a synced blockchain.
4. **Network**:
   * **Stable broadband connection with at least 25 Mbps**. A reliable and fast internet connection is essential for maintaining connectivity with the network and processing transactions efficiently.
5. **Operating System**:
   * **Linux (Ubuntu or Debian recommended), macOS, or Windows**. Most Ethereum clients are optimized for Linux, making it the preferred operating system for running validator nodes.
6. **Power Supply**:
   * The power requirements are much lower since PoS validators do not require intense computational power. A standard power supply unit that supports the above components is sufficient.

### Additional Considerations

* **Backup and Security**: Since validators must keep their private keys secure, consider using hardware security modules (HSMs) or secure offline storage (cold wallets) for private keys.
* **Redundancy**: For those seeking to operate a highly available node, consider setting up failover systems or backup internet connections to ensure continuous operation.

