# Nodes

A "node" is a computer connected to other computers, forming a peer-to-peer network. A node has to run two clients: a [consensus client](nodes-and-clients.md#consensus-clients) and an [execution client](nodes-and-clients.md#execution-clients).Different types of nodes consume data differently. Clients can run three different types of nodes: light, full, and archive. There are also options for different synchronization strategies, of nodes that consume data differently. Clients can run three different types of nodes: light, full, and archive. There are also options for different [synchronization strategies](nodes-and-clients.md) which enable faster synchronization time. Synchronization refers to how quickly it can get the most up-to-date information on the state of the network, such as Ethereum or Nephele.

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

An archive node (see [full archive sync client](nodes-and-clients.md#full-archive)) is crucial for understanding the concept of "state" in Ethereum and Nephele, which functions as a transaction-based state machine. Here, the state encompasses all the global data, such as account balances, contract code and storage, and other consensus-related data, all stored within a trie database managed by the execution layer client.

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

Light nodes are simply running a[ light sync client](nodes-and-clients.md#light). Light nodes enable users to participate in the network without the powerful hardware or high bandwidth required to run full nodes. Eventually, light nodes might run on mobile phones or embedded devices. The light nodes do not participate in consensus (i.e. they cannot be miners/validators). Still, they can access the blockchain with the same functionality and security guarantees as a full node. Potential routes to providing light client data over the [gossip network](https://www.ethportal.net/) in Ethereum and can have similar interests in Nephele.

### WHY SHOULD I RUN AN ETHEREUM NODE? <a href="#why-should-i-run-an-ethereum-node" id="why-should-i-run-an-ethereum-node"></a>

Running a node allows you to directly, trustlessly and privately use Ethereum while supporting the network by keeping it more robust and decentralized.

#### Benefits to you <a href="#benefits-to-you" id="benefits-to-you"></a>

Running your own node enables you to use Ethereum in a private, self-sufficient and trustless manner. You don't need to trust the network because you can verify the data yourself with your client. "Don't trust, verify" is a popular blockchain mantra.

* Your node verifies all the transactions and blocks against consensus rules by itself. This means you don’t have to rely on any other nodes in the network or fully trust them.
* You can use an Ethereum wallet with your own node. You can use dapps more securely and privately because you won't have to leak your addresses and balances to intermediaries. Everything can be checked with your own client. [MetaMask(opens in a new tab)](https://metamask.io/), [Frame(opens in a new tab)](https://frame.sh/), and [many other wallets](https://ethereum.org/en/wallets/find-wallet/) offer RPC-importing, allowing them to use your node.
* You can run and self-host other services which depend on data from Ethereum. For example, this might be a Beacon Chain validator, software like layer 2, infrastructure, block explorers, payment processors, etc.
* You can provide your own custom [RPC endpoints](https://ethereum.org/en/developers/docs/apis/json-rpc/). You could even offer these endpoints publicly to the community to help them avoid big centralized providers.
* You can connect to your node using **Inter-process Communications (IPC)** or rewrite the node to load your program as a plugin. This grants low latency, which helps a lot, e.g. when processing a lot of data using web3 libraries or when you need to replace your transactions as fast as possible (i.e. frontrunning).
* You can directly stake ETH to secure the network and earn rewards. See [solo staking](https://ethereum.org/en/staking/solo/) to get started.

<figure><img src="https://ethereum.org/_next/image/?url=%2Fcontent%2Fdevelopers%2Fdocs%2Fnodes-and-clients%2Fnodes.png&#x26;w=1920&#x26;q=75" alt=""><figcaption></figcaption></figure>

#### Network benefits <a href="#network-benefits" id="network-benefits"></a>

A diverse set of nodes is important for Ethereum’s health, security and operational resiliency.

* Full nodes enforce the consensus rules so they can’t be tricked into accepting blocks that don't follow them. This provides extra security in the network because if all the nodes were light nodes, which don't do full verification, validators could attack the network.
* In case of an attack which overcomes the crypto-economic defenses of [proof-of-stake](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/#what-is-pos), a social recovery can be performed by full nodes choosing to follow the honest chain.
* More nodes in the network result in a more diverse and robust network, the ultimate goal of decentralization, which enables a censorship-resistant and reliable system.
* Full nodes provide access to blockchain data for lightweight clients that depend on it. Light nodes don't store the whole blockchain, instead they verify data via the [state roots in block headers](https://ethereum.org/en/developers/docs/blocks/#block-anatomy). They can request more information from full nodes if they need it.

If you run a full node, the whole Ethereum network benefits from it, even if you don't run a validator.

### RUNNING YOUR OWN NODE <a href="#running-your-own-node" id="running-your-own-node"></a>

Interested in running your own Ethereum client?

For a beginner-friendly introduction visit our [run a node](https://ethereum.org/en/run-a-node/) page to learn more.

If you're more of a technical user, dive into more details and options on how to [spin up your own node](https://ethereum.org/en/developers/docs/nodes-and-clients/run-a-node/).

### ALTERNATIVES <a href="#alternatives" id="alternatives"></a>

Setting up your own node can cost you time and resources but you don’t always need to run your own instance. In this case, you can use a third party API provider. For an overview of using these services, check out [nodes as a service](https://ethereum.org/en/developers/docs/nodes-and-clients/nodes-as-a-service/).

If somebody runs an Ethereum node with a public API in your community, you can point your wallets to a community node via Custom RPC and gain more privacy than with some random trusted third party.

On the other hand, if you run a client, you can share it with your friends who might need it.

#### Tracking nodes in the network <a href="#network-overview" id="network-overview"></a>

Multiple trackers offer a real-time overview of nodes in the Ethereum network. Note that due to the nature of decentralized networks, these crawlers can only provide a limited view of the network and might report different results.

* [Map of nodes(opens in a new tab)](https://etherscan.io/nodetracker) by Etherscan
* [Ethernodes(opens in a new tab)](https://ethernodes.org/) by Bitfly
* [Ethereum Node Crawler(opens in a new tab)](https://crawler.ethereum.org/)
* [Nodewatch(opens in a new tab)](https://www.nodewatch.io/) by Chainsafe, crawling consensus nodes

