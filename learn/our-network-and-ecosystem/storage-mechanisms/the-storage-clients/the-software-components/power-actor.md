# Power Actor

The **Power Actor** in Filecoin is a core component that manages the **storage power** of each **storage provider (miner)** in the network. Storage power measures the amount of verifiable storage a miner contributes to the Filecoin network. The Power Actor is responsible for keeping track of each miner's storage power, directly affecting their probability of winning block rewards and their overall influence in the network's consensus mechanism.

<mark style="color:red;">It is an abstracted entity, a</mark> <mark style="color:red;"></mark><mark style="color:red;">**pure software component**</mark> <mark style="color:red;"></mark><mark style="color:red;">implemented in Lotus client (or equivalent).</mark>

## **Key Functions of the Power Actor in Filecoin**

#### **Storage Power Accounting**

The Power Actor tracks and records the amount of **storage power** each miner contributes to the network. Storage power is proportional to the amount of storage a miner has committed and proven to be storing correctly through **Proof-of-Replication (PoRep)** and **Proof-of-Spacetime (PoSt)**.

Miners with more storage power are more likely to be selected to mine new blocks and earn block rewards. This incentivizes storage providers to commit more storage to the network.

#### **Manages Storage Power and Consensus Participation**

The Power Actor determines which miners can participate in the network’s consensus process ([**Expected Consensus**](../../expected-consensus.md) in Filecoin). To be eligible for block mining, miners must maintain a certain level of storage power.

Storage power influences a miner’s probability of being selected to propose a new block, directly impacting their potential earnings from block rewards.

#### **Onboarding and Dropping Miners**

The Power Actor is responsible for **adding new miners** to the network when they commit their initial storage and **removing miners** from the network when they fall below a certain threshold of storage power or fail to meet the network's requirements.

This ensures that only active and compliant miners are counted towards the network’s storage power.

#### **Calculates and Updates Network Total Power**

The Power Actor maintains the **total network storage power**, which is the sum of the storage power of all active miners. This metric is crucial for determining the overall health and storage capacity of the Filecoin network.

It updates the network total power dynamically as miners add or remove storage or when sectors are lost due to faults or expirations.

#### **Handles Power with Penalties and Faults**

The Power Actor adjusts a miner's storage power based on **fault penalties**, such as failing to submit a **Proof-of-Spacetime (PoSt)** or losing committed data. These penalties can reduce a miner's storage power, affecting their ability to win block rewards and maintain their standing in the network.

Faults can lead to the **temporary or permanent reduction** of a miner’s storage power, depending on the severity and type of fault.

#### **Interacts with Other Actors**

The Power Actor interacts with other actors, such as the **Storage Miner Actor** (which manages the miner’s storage operations) and the **Reward Actor** (which handles block rewards distribution based on storage power). It coordinates with these actors to ensure that storage power reflects the true state of each miner's contributions.

#### **Facilitates Consensus Security and Decentralization**

By accurately tracking storage power and ensuring that only compliant miners participate in consensus, the Power Actor helps maintain the **security and decentralization** of the Filecoin network. It ensures that the consensus mechanism remains fair and that block rewards are distributed proportionally to the storage provided.

#### **Manages Pledge Requirements**

The Power Actor manages the **initial pledge collateral** miners must lock up to participate in the network. This collateral is required to ensure miners are committed to maintaining their storage and not engaging in malicious behavior.

## **Technical Overview**

* **Built-in Actor:**\
  The Power Actor is a built-in actor in the Filecoin protocol, implemented in **Lotus** and other Filecoin clients. It is an essential component that ensures the proper functioning of the network's storage-based consensus mechanism.
* **Smart Contract-Like Functionality:**\
  Like other actors, the Power Actor functions like a smart contract that manages state, enforces rules, and coordinates with other actors to maintain network integrity.

The Filecoin Power Actor is responsible for managing miners' storage power, which is critical for network consensus, block reward distribution, and overall network security. It tracks each miner's storage power, calculates the total network power, handles penalties and faults, and ensures that only compliant miners participate in the Filecoin network.
