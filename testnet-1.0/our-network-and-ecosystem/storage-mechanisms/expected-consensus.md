# Expected Consensus

**Expected Consensus** is the consensus mechanism used by the Filecoin network to achieve decentralized agreement on the state of the blockchain (also knwon as storage power consensus). It combines concepts from **Proof-of-Replication (PoRep)**, **Proof-of-Spacetime (PoSt)**, and traditional **Nakamoto consensus** (like that used in Bitcoin) to provide a storage-based consensus protocol that incentivizes decentralized storage and ensures data integrity.

## **Key Concepts of Expected Consensus in Filecoin**

1. **Storage Power-Based Leader Election:**
   * In Expected Consensus, block miners (storage providers) are chosen to propose new blocks based on their **storage power**. Storage power represents the amount of verifiable storage a miner contributes to the Filecoin network.
   * The more storage a miner has committed and proven, the higher their **probability of being selected** to mine a new block. This probability is proportional to the miner’s share of the total network storage power.
2. **Winning Proof-of-Spacetime (PoSt):**
   * **WinningPoSt:** Miners must regularly generate **Proof-of-Spacetime (PoSt)** to prove that they continuously store the committed data over time. Failure to submit valid PoSts results in penalties and a reduction in storage power, affecting the miner's eligibility to participate in the consensus.
3. **Block Mining and Chain Selection:**
   * Miners selected to propose new blocks do so by appending them to the **longest valid chain** they know. The chain with the most **storage power-weighted votes** (blocks) is canonical.
   * Miners are incentivized to extend the chain that is most likely to be adopted by the network, ensuring convergence and consistency.
4. **Block Reward and Penalty Mechanisms:**
   * Miners who successfully mine a block are rewarded with **block rewards** (in FIL tokens) and any **transaction fees** included in the block.
   * To discourage malicious behavior and ensure data availability, miners are subject to **penalties** for faults, such as failing to produce a valid PoSt or losing client data. Penalties can include losing a portion of their collateral and reducing their storage power.
5. **Chain Quality and Weighting:**
   * Each block contributes to the **chain quality** by representing the storage power of the miner who mined it. The chain with the highest cumulative weight (i.e., the most storage power-backed blocks) is considered the heaviest chain and, therefore, the canonical chain.
   * This mechanism aligns incentives for miners to follow the protocol honestly and maintain the integrity of the blockchain.
6. **Tipset-Based Mining:**
   * **Tipsets** are blocks mined at the same epoch (time slot) but by different miners. Expected Consensus allows multiple miners to propose blocks simultaneously, which are then included in a **tipset**.
   * The tipset model improves network throughput by allowing multiple blocks to be processed at the same time, making the consensus mechanism more scalable.
7. **Fork Resolution:**
   * When forks occur (i.e., competing chains are created), the network uses the **Expected Consensus rules** to determine the heaviest chain based on the total storage power. Miners will build on the chain with the highest weight, and lighter chains will eventually be discarded.
8. **Security Against Attacks:**
   * Expected Consensus is designed to be secure against various attacks, such as **Sybil attacks** (creating fake identities), by requiring significant storage commitments and cryptographic proofs.
   * The use of storage power rather than hash power (as in proof-of-work systems like Bitcoin) makes it more costly to attack the network, as an attacker would need to control a significant portion of the network’s storage.

## **Technical Overview**

* **Combination of Proofs and Probabilistic Selection:**\
  Expected Consensus relies on cryptographic proofs (PoRep and PoSt) and a probabilistic leader election mechanism based on storage power. This creates a system where data storage directly impacts consensus participation and rewards.
* **Block Validity and Chain Growth:**\
  Only blocks that adhere to the protocol rules (valid PoReps, PoSts, and transactions) contribute to the chain's growth, ensuring security and integrity.
* **Implemented in Lotus and Other Clients:**\
  The Expected Consensus algorithm is implemented in **Lotus** and other Filecoin clients, following the protocol specifications defined by the Filecoin network.

**Expected Consensus** in Filecoin is a storage power-based consensus mechanism that uses cryptographic proofs (PoRep and PoSt) to ensure data integrity and incentivize decentralized storage. It selects miners to propose new blocks probabilistically based on their storage power, uses tipsets to improve throughput, and maintains network security through penalties and rewards. This approach ensures a secure, scalable, and decentralized storage network.
