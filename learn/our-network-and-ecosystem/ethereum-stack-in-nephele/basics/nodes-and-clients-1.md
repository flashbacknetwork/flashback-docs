# Nodes

A "node" is a computer connected to other computers, forming a peer-to-peer network. A node has to run two clients: a [consensus client](nodes-and-clients.md#consensus-clients) and an [execution client](nodes-and-clients.md#execution-clients).Different types of nodes consume data differently. Clients can run three different types of nodes: light, full, and archive. There are also options for different synchronization strategies, of nodes that consume data differently. Clients can run three different types of nodes: light, full, and archive. There are also options for different [synchronization strategies](nodes-and-clients.md) which enable faster synchronization time. Synchronization refers to how quickly it can get the most up-to-date information on the state of the network, such as Ethereum or Flashback.

***

## Full node <a href="#full-node" id="full-node"></a>

Full nodes are essential components of a blockchain network, performing the critical function of block-by-block validation. This includes the comprehensive task of downloading and verifying each block's body and state data. Full nodes ensure the integrity and consistency of the blockchain by confirming that all transactions and block contents adhere to the network rules.

There are various classes of full nodes, each differing in how they sync with the blockchain:

1. <mark style="color:orange;">**Classic Full Nodes**</mark>: These nodes start syncing from the genesis block and methodically verify every single block up to the present. This method ensures the highest level of data integrity but can be resource-intensive and time-consuming.
2. <mark style="color:orange;">**Modern Sync Methods**</mark> (see '[snap sync](nodes-and-clients.md#full-snapshot)')**:** These nodes begin validating from a trusted, more recent block. This approach significantly speeds up the synchronization process by avoiding revalidation the entire blockchain history.

Regardless of the synchronization method, full nodes typically only retain some historical data for a while. Instead, they keep only a local copy of the most recent data—often the last 128 blocks—which allows them to save disk space by deleting older data that is less frequently accessed. However, these older blocks and state data are not lost; they can be regenerated from saved 'snapshots' when needed. This pruning process helps manage the node’s storage efficiently while supporting the network's demands.

Full nodes play several vital roles in the blockchain ecosystem:

* <mark style="color:purple;">**Data Verification:**</mark> They participate actively in block validation, ensuring every block and state transition is legitimate.
* <mark style="color:purple;">**Network Support:**</mark> By serving verified data on request, they help maintain the blockchain's operational continuity and reliability.
* <mark style="color:purple;">**Decentralization and Security:**</mark> By independently verifying and storing data, full nodes contribute to the network's decentralization and enhance its resilience against attacks or failures.

Overall, full nodes are foundational to the blockchain's function and security, ensuring the network remains robust, accurate, and trustworthy.

***

## Archive node <a href="#archive-node" id="archive-node"></a>

An archive node (see [full archive sync client](nodes-and-clients.md#full-archive)) is crucial for understanding the concept of "state" in Ethereum and Flashback, which functions as a transaction-based state machine. Here, the state encompasses all the global data, such as account balances, contract code and storage, and other consensus-related data, all stored within a trie database managed by the execution layer client.

### **Why Full Nodes and Archive Nodes Differ**

Full nodes play a vital role by downloading, verifying, and storing each block's body and state data. While most full nodes sync from the genesis block and continuously verify each block, some, like those using Geth's 'snap sync', start from a trusted recent block. Typically, full nodes keep only the recent state (e.g., the last 128 blocks) to manage chain reorganizations and provide quick access to recent data. This makes them efficient for everyday tasks like transaction verification and block production but not for accessing historical data.

<mark style="color:green;">In contrast, archive nodes store not just recent states but every historical state from each block.</mark> They trade more extensive disk space for the ability to provide immediate access to any historical state without re-executing transactions. This is particularly useful for users who need to query historical data frequently, such as for checking the balance of an account at a specific block in the past.

### **Use Cases for Archive Nodes**

Regular network users typically don't need archive nodes for standard network interactions like sending transactions or deploying contracts. However, archive nodes are invaluable for:

* Service providers like block explorers that need to offer historical data.
* Researchers and security analysts who analyze past network activities.
* DApp developers and auditors who require access to historical states for testing and compliance checks.

Depending on the client, running an archive node involves different configurations, sync times, and database sizes. It's important to choose the right client based on how efficiently it handles the vast amount of data. For example, while some clients may require over 12TB of space, others like Erigon can operate under 3TB.

Given their extensive data needs, archive nodes require substantial disk space ranging from 3TB to 12TB, making SSDs a necessity for efficiency. It's also advisable to use high-quality, reliable SATA drives and consider configurations like RAID0 or ZFS for data integrity. While more RAM can expedite synchronization, the CPU speed is critical during the initial sync, which can take up to a month on consumer-grade hardware.

## Light node <a href="#light-node" id="light-node"></a>

Light nodes are simply running a[ light sync client](nodes-and-clients.md#light). Light nodes enable users to participate in the network without the powerful hardware or high bandwidth required to run full nodes. Eventually, light nodes might run on mobile phones or embedded devices. They can access the blockchain with the same functionality and security guarantees as a full node. Potential routes to providing light client data over the [gossip network](https://www.ethportal.net/) in Ethereum and can have similar interests in Flashback.

### **Differences Between Light Nodes and Full Nodes Regarding Rewards:**

**Full Nodes** can participate as validators. Validators are selected to propose and attest to new blocks based on their stake in the network (the amount of ETH they have staked). Validators earn rewards for performing these duties correctly, and they can lose some of their stake (through slashing) if they act maliciously or negligently.

**Light Nodes** do not have the full blockchain and are not involved in validating the blockchain in the same way full nodes are. Therefore, they do not earn rewards from block production or validation.

### **Role of Light Nodes:**

* **Data Access:** Light nodes are primarily used to access blockchain data without the overhead of storing the entire blockchain. They are often used in environments with limited storage and computational resources, like mobile devices or lightweight clients.
* **No Reward Mechanism:** In the Ethereum protocol, light nodes are not rewarded because they do not contribute to the network's security by validating transactions or blocks.

## Tracking nodes in the network <a href="#network-overview" id="network-overview"></a>

Multiple trackers offer a real-time overview of nodes in the Ethereum network. We expect to find solutions for Flashback and its ecosystem development. Note that due to the nature of decentralized networks, these crawlers can only provide a limited view of the network and might report different results.

* TBD
