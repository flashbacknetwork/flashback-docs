# Reward Actor

The **Reward Actor** in Filecoin is a core component that handles the distribution of **block rewards** to **storage providers (miners)** who contribute to the network by storing data and participating in the network’s consensus mechanism. The Reward Actor is responsible for managing the issuance and distribution of rewards based on the consensus rules and ensuring that incentives are aligned to maintain network security and growth.

## **Key Functions of the Reward Actor in Filecoin**

#### **Distributes Block Rewards to Miners**

The primary function of the Reward Actor is to distribute **block rewards** to miners who successfully mine a block and include it in the Filecoin blockchain. These rewards are paid out in **FIL**, the native cryptocurrency of the Filecoin network.

Block rewards are the primary incentive for miners to commit storage and participate in the consensus process (Expected Consensus). The more storage power a miner contributes, the higher their probability of mining a block and earning a reward.

#### **Computes Block Reward Amounts**

* The Reward Actor calculates the amount of FIL to be distributed as block rewards based on a **pre-defined schedule** that gradually decreases the issuance rate over time. This is similar to the concept of **block subsidies** in Bitcoin or Ethereum, where the reward per block reduces as the network matures.
* The reward amount is determined using an **exponential decay function**, which aims to align incentives for miners while controlling the long-term inflation of the FIL token supply.

#### **Facilitates Baseline and Simple Minting Models**

The Reward Actor utilizes a dual reward model that includes:

* **Simple Minting:** Directly rewards miners based on the total storage power they provide. This component is straightforward and scales with the amount of storage committed to the network.
* **Baseline Minting:** Encourages network growth by issuing additional rewards when the network’s total storage power exceeds certain predefined **baseline targets**. These targets are set to stimulate growth in network storage capacity over time.

This dual model incentivizes both new and existing miners to continue expanding their storage and contributing to network security.

#### **Updates Miner Balances**

* Upon the successful mining of a block, the Reward Actor updates the balance of the miner’s **Storage Miner Actor** account by adding the corresponding block reward. The miner can then use these rewards for various purposes, such as collateralizing new storage deals, covering operational costs, or withdrawing to their personal accounts.

#### **Interacts with the Power Actor**

* The Reward Actor coordinates closely with the **Power Actor** to ensure that rewards are distributed in proportion to a miner’s **storage power**. Miners with more storage power have a higher chance of mining a block and thus receiving rewards.
* The Power Actor maintains accurate records of each miner’s storage power, which is critical for determining their share of block rewards.

#### **Ensures Security and Fairness in Reward Distribution**

* By using the **Expected Consensus** mechanism, the Reward Actor ensures that rewards are distributed fairly among miners who follow the protocol rules. Miners who fail to provide valid proofs or engage in malicious behavior are penalized and may lose their eligibility for rewards.
* The reward distribution mechanism is designed to prevent **centralization** by encouraging more miners to join and contribute to the network.

#### **Handles Vesting Schedules**

* A portion of the block rewards may be subject to **vesting schedules** to align long-term incentives. This means that not all rewards are immediately liquid; some are vested over time to encourage miners to remain committed to the network and avoid short-term behavior.

#### **Technical Overview:**

* **Built-in Actor:**\
  The Reward Actor is one of the **built-in actors** within the Filecoin protocol, implemented in the **Lotus** client and other compatible clients.
* **Smart Contract-Like Functionality:**\
  It functions like a smart contract, managing state and enforcing rules for reward issuance and distribution.
* **On-Chain Reward Management:**\
  The entire process of reward calculation, distribution, and updating miner balances is handled on-chain to ensure transparency, security, and immutability.

#### **Summary:**

The **Reward Actor** in Filecoin is a core component that distributes block rewards to miners based on their storage power and participation in the network’s consensus mechanism. It calculates rewards using a dual model (simple minting and baseline minting), interacts with the Power Actor to ensure fairness, and updates miner balances accordingly. The Reward Actor plays a crucial role in incentivizing decentralized storage and maintaining the security and growth of the Filecoin network.
