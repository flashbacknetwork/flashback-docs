# Network Protocol Clients

A client is an implementation of Ethereum that verifies data against the protocol rules and keeps the network secure. A node has to run two clients: a consensus client and an execution client.

* <mark style="color:yellow;">Execution client</mark> listens to new transactions broadcasted in the network, executes them in EVM, and holds the latest state and database of the decentralized ledger.
* <mark style="color:yellow;">Consensus client</mark> implements the consensus algorithm, which enables the network to achieve agreement based on validated data from the execution client.&#x20;

<mark style="color:green;">**Nephele forked the Ethereum stack and inherited it from its property. Hence, these clients work together to keep track of the head of the Nephele blockchain and allow users to interact with the network.**</mark>&#x20;

The modular design with multiple pieces of software working together is called [encapsulated complexity](https://vitalik.eth.limo/general/2022/02/28/complexity.html). This approach made it easier to execute [The Merge](https://ethereum.org/en/roadmap/merge/) in Ethereum seamlessly, makes client software more accessible to maintain and develop, and enables the reuse of individual clients, for example, in the [layer 2 ecosystem](https://ethereum.org/en/layer-2/).

<figure><img src="https://ethereum.org/_next/image/?url=%2Fcontent%2Fdevelopers%2Fdocs%2Fnodes-and-clients%2Feth1eth2client.png&#x26;w=1920&#x26;q=75" alt=""><figcaption><p>An illustration of the client ecosystem in Ethereum that applied for Nephele</p></figcaption></figure>

## Client Diversity <a href="#client-diversity" id="client-diversity"></a>

Execution and consensus clients exist in various programming languages developed by different teams. This diversity has multiple reasons, such as bug discovery or blockchain security, and allows the creation of a competitive interaction with the protocol.&#x20;

What these implementations have in common is they all follow a single specification. Specifications dictate how the network and blockchain function. Every technical detail is defined and specifications can be found concerning the Ethereum network as:

* Originally, the [Ethereum Yellow Paper](https://ethereum.github.io/yellowpaper/paper.pdf)
* [Execution specs](https://github.com/ethereum/execution-specs/)
* [Consensus specs](https://github.com/ethereum/consensus-specs)
* [EIPs](https://eips.ethereum.org/) implemented in various [network upgrades](https://ethereum.org/en/history/)

### Why multiple clients?

Having a variety of client implementations can fortify a network by lessening its reliance on a single codebase. The ultimate aim is to foster a balanced client ecosystem where no single client overshadows the others, thereby mitigating the risk of a singular point of failure.&#x20;

This diversity not only attracts a wider range of developers by allowing them to work in their preferred programming languages but also enhances the potential for more robust integrations. However, simply offering multiple clients is not sufficient; it's crucial that these clients are actively adopted and used by the community, ensuring that the distribution of active nodes remains fairly even across different clients.

### Why is client diversity important? <a href="#client-diversity-importance" id="client-diversity-importance"></a>

#### 1. Bugs <a href="#bugs" id="bugs"></a>

A flaw in a single client poses less risk to the overall network when that client represents only a small fraction of network nodes. Maintaining a balanced node distribution among various clients reduces the chances that multiple clients will encounter a common problem. Consequently, this diversity enhances the robustness and stability of the network.

#### 2. Resilience to attacks <a href="#resilience" id="resilience"></a>

Diversity among clients enhances network resilience against certain [attacks](https://x.com/vdWijden/status/1437712249926393858). For instance, if an attack targets a specific client to divert it onto an incorrect chain branch, it's unlikely to impact the network significantly because other clients not sharing the same vulnerability would maintain the integrity of the canonical chain. Low diversity in client distribution heightens the risk of network disruption if the predominant client is compromised.&#x20;

A practical example in the Ethereum network of the benefits of client diversity was observed during the 2016 Shanghai denial-of-service attack. In this incident, the primary client, Geth, was manipulated to excessively perform slow disk input/output operations. Fortunately, the presence of alternative clients, which did not have this vulnerability, allowed the network to continue functioning while the issue with Geth was addressed.

#### 3. Consensus finality <a href="#finality" id="finality"></a>

A consensus client controlling more than <mark style="color:orange;">33% of network nodes</mark> could disrupt the finalization of the consensus layer, casting doubt on the reliability of transaction finality. This uncertainty could severely impact applications built on the network, especially those in the DeFi sector.&#x20;

Even more concerning, if a critical bug affects a client that commands a two-thirds majority, it could erroneously cause the blockchain to split and finalize on an incorrect path, trapping many validators on an invalid chain. To rejoin the correct chain, the network integrates severe penalties to the validators, or they may need to undergo a costly and time-consuming process of voluntary withdrawal and reactivation.

While such scenarios are uncommon, the network ecosystem can reduce their likelihood by promoting a more balanced distribution of clients across the active nodes, ensuring that no single consensus client amasses a 33% share of the total nodes.

#### 4. Shared responsibility <a href="#responsibility" id="responsibility"></a>

Having a single client dominate the network also carries significant human costs. It places undue pressure and responsibility on a small group of developers. When client diversity is limited, this small team bears an outsized burden, which can be overwhelming. Distributing this responsibility among several development teams alleviates this strain and benefits the overall health of node network and its community of contributors.

## Execution Clients <a href="#execution-clients" id="execution-clients"></a>

The Ethereum community maintains multiple open-source execution clients (previously known as 'Eth1 clients', or just 'Ethereum clients'), developed by different teams using different programming languages. The ideal goal is to achieve diversity without any client dominating to reduce any single points of failure.

This table summarizes the different clients. All of them pass [client tests](https://github.com/ethereum/tests) and are actively maintained to stay updated with network upgrades. For more on supported networks, read up on [Ethereum networks](https://ethereum.org/en/developers/docs/networks/).

Each client has unique use cases and advantages, so you should choose one based on your own preferences. Diversity allows implementations to be focused on different features and user audiences. You may want to choose a client based on features, support, programming language, or licences.

<table data-view="cards"><thead><tr><th>Client</th><th>Language</th><th>Operating systems</th><th>Networks</th><th>Sync strategies</th><th>State pruning</th><th>Description</th></tr></thead><tbody><tr><td><a href="https://geth.ethereum.org/">Geth</a></td><td>Go</td><td>Linux, Windows, macOS</td><td>Mainnet, Sepolia, Holesky</td><td>Snap, Full</td><td>Archive, Pruned</td><td><p>Hyperledger Besu is an enterprise-grade Ethereum client for public and permissioned networks. It runs all of the Ethereum Mainnet features, from tracing to GraphQL. It has extensive monitoring and is supported by ConsenSys, both in open community channels and through commercial SLAs for enterprises. It is written in Java and is Apache 2.0 licensed. </p><p>Besu's extensive <a href="https://besu.hyperledger.org/en/stable/">documentation</a> will guide you through all details on its features and setups.</p></td></tr><tr><td><a href="http://nethermind.io/">Nethermind</a></td><td>C#, .NET</td><td>Linux, Windows, macOS</td><td>Mainnet, Sepolia, Holesky</td><td>Snap (without serving), Fast, Full</td><td>Archive, Pruned</td><td>Erigon, formerly known as Turbo‐Geth, started as a fork of Go Ethereum oriented toward speed and disk‐space efficiency. Erigon is an utterly re-architected implementation of Ethereum, currently written in Go but with implementations in other languages under development. Erigon's goal is to provide a faster, more modular, and more optimized implementation of Ethereum. It can perform a full archive node sync using around 2TB of disk space in under 3 days. Learn more about Nethermind in its <a href="https://docs.nethermind.io/">documentation</a>.</td></tr><tr><td><a href="https://besu.hyperledger.org/en/stable/">Besu</a></td><td>Java</td><td>Linux, Windows, macOS</td><td>Mainnet, Sepolia, Holesky</td><td>Snap, Fast, Full</td><td>Archive, Pruned</td><td><p>Go Ethereum (Geth for short) is one of the original implementations of the Ethereum protocol. It is the most widespread client with the most extensive user base and variety of tooling for users and developers. It is written in Go, fully open source and licensed under the GNU LGPL v3.</p><p>Learn more about Geth in its <a href="https://geth.ethereum.org/docs/">documentation</a>.</p></td></tr><tr><td><a href="https://github.com/ledgerwatch/erigon">Erigon</a></td><td>Go</td><td>Linux, Windows, macOS</td><td>Mainnet, Sepolia, Holesky</td><td>Full</td><td>Archive, Pruned</td><td><p>Nethermind is an Ethereum implementation created with the C# .NET tech stack, licensed with LGPL-3.0, and running on all major platforms, including ARM. It offers excellent performance with:</p><ul><li>Optimized virtual machine</li><li>State access</li><li>Networking and rich features like Prometheus/Grafana dashboards, seq enterprise logging support, JSON RPC tracing, and analytics plugins.</li></ul><p>Nethermind also has <a href="https://docs.nethermind.io/">detailed documentation</a>, strong dev support, an online community, and 24/7 support for premium users.</p></td></tr><tr><td><a href="https://github.com/paradigmxyz/reth">Reth</a> <em>(beta)</em></td><td>Rust</td><td>Linux, Windows, macOS</td><td>Mainnet, Sepolia, Holesky</td><td>Full</td><td>Archive, Pruned</td><td>Reth is an Ethereum client designed to enhance the performance and scalability of Ethereum networks. It's part of the suite of tools that interact with the Ethereum blockchain, enabling users to send transactions, deploy smart contracts, and connect to the network. Reth focuses on providing a robust and efficient way for developers and users to engage with Ethereum, contributing to the ecosystem's diversity and resilience. Like other Ethereum clients, it plays a crucial role in processing and verifying transactions, maintaining the blockchain’s integrity, and ensuring network security. Explore Reth with their <a href="https://reth.rs/">documentation</a>.</td></tr><tr><td><a href="https://github.com/ethereumjs/ethereumjs-monorepo">EthereumJS</a> <em>(beta)</em></td><td>TypeScript</td><td>Linux, Windows, macOS</td><td>Sepolia, Holesky</td><td>Full</td><td>Pruned</td><td><p>The EthereumJS Execution Client (EthereumJS) is written in TypeScript and composed of several packages. These include core Ethereum primitives represented by the Block, Transaction, and Merkle-Patricia Trie classes and core client components, including an implementation of the Ethereum Virtual Machine (EVM), a blockchain class, and the DevP2P networking stack.</p><p> You can learn more about it by reading its <a href="https://github.com/ethereumjs/ethereumjs-monorepo/tree/master">documentation</a>.</p></td></tr></tbody></table>

The Ethereum client needs to sync with the latest network state to follow and verify current data. This is done by downloading data from peers, cryptographically verifying their integrity, and building a local blockchain database. On the execution layer, we can observe three different synchronization modes:

### **Full archive**

<mark style="color:yellow;">Full archive synchronization (Full sync or Full client)</mark> downloads all blocks information (including headers, transactions, and receipts) and generates the state of the blockchain incrementally by executing every block from genesis.

* Minimizes trust and offers the highest security by verifying every transaction.
* With an increasing number of transactions, processing all transactions can take days to weeks.

### **Full snapshot**

<mark style="color:yellow;">Full snapshot synchronization (snap sync or snap client)</mark> \[more [here](https://github.com/ethereum/devp2p/blob/master/caps/snap.md)] operates similarly to a full archive synchronization by verifying each block in the blockchain. However, unlike full syncs that begin at the genesis block, snap sync starts from a recent, verified checkpoint believed to be a reliable part of the blockchain. Employing snap sync demand to periodically saves these checkpoints and removes data that exceeds a certain age. This method allows nodes to recreate state data from these snapshots when necessary, rather than maintaining a permanent record of all state data.

* Fastest sync strategy, currently default in Ethereum mainnet
* Saves a lot of disk usage and network bandwidth without sacrificing security

### **Light**

<mark style="color:yellow;">Light synchronization (light sync or light client)</mark> involves downloading all block headers and selectively verifying block data. Rather than maintaining an independent, local copy of all blockchain data and verifying every change, a light sync requests the necessary data from a provider. This provider could be directly connected to a machine running a full sync client or accessed through a centralized RPC server.&#x20;

The light sync client then verifies this data, keeping it updated with the latest chain developments. Light sync clients primarily process block headers and only occasionally download the actual contents of blocks. The extent of a client's "lightness" depends on the mix of light and full client software it utilizes. For instance, many operators may combine light clients with full snap or archive clients or the other way around, depending on their specific needs and resources.

* Gets only the latest state while relying on trust in developers and consensus mechanisms.
* The client will be ready to use the current network state in a few minutes.

#### How does light sync work technically?

When Ethereum transitioned to a proof-of-stake consensus mechanism, it introduced specific infrastructure to enhance support for light clients. The system operates by designating a **sync committee**, a randomly selected group of 512 validators, every 1.1 days.&#x20;

This committee is responsible for signing the headers of recent blocks. Each block header includes the collective signature from the sync committee members, along with a "bitfield" indicating which validators participated in the signing. Additionally, the header lists the validators expected to sign the next block. This setup allows light clients to verify the authenticity of the data they receive by checking if the current sync committee's signature matches the expected committee detailed in the previous block's header. Thus, light clients can continually update their understanding of the latest Ethereum block by only downloading the header, which contains summarized information.

A lot of work is also being done to improve how light clients can access network data. Currently, light clients rely on RPC requests to full sync nodes using a client/server model, but in the future the data could be requested in a more decentralized way using a dedicated network such as the [Portal Network](https://www.ethportal.net/) that could serve the data to light clients using a peer-to-peer gossip protocol.

Other [roadmap](https://ethereum.org/en/roadmap/) items such as [Verkle trees](https://ethereum.org/en/roadmap/verkle-trees/) and [statelessness](https://ethereum.org/en/roadmap/statelessness/) will eventually bring the security guarantees of light clients equal to those of full clients.

#### Why is this important?

Light clients are crucial as they enable users to independently verify the accuracy of their data without fully trusting external data providers, all while consuming a fraction of the resources needed by a full node. These clients validate data against block headers, which are authenticated by at least two-thirds of a selected group of 512 Ethereum validators, providing strong assurance of data integrity.

Operating with minimal computing power, memory, and storage, light clients are versatile enough to run on mobile devices, within apps, or browsers. This setup offers a trust-minimized way to access Ethereum, reducing reliance on third-party providers.

_Example: Checking an Ethereum or Nephele account balance. This would require querying a node directly or through a centralized service, relying on their integrity for accurate information. Light clients, however, allow users to verify this data themselves. They receive data along with cryptographic proof, which the light client can cross-check against its block header information, ensuring the data’s validity directly from the network rather than a third-party._

#### Use cases with light clients

Light clients significantly enhance the blockchain network access by requiring minimal hardware, reducing dependence on third-party providers. This not only empowers users to verify their data but also bolsters the network by increasing the number and diversity of nodes validating the blockchain.

Light clients facilitate the operation of Ethereum nodes on devices with limited storage, memory, and processing capabilities. Innovations allow these clients to be integrated into browsers, run on mobile phones, or even smaller devices like smartwatches, leading to more decentralized mobile wallets.

Furthermore, <mark style="color:purple;">**light clients extend capabilities to Internet of Things (IoT) devices**</mark>. For instance, an app with an embedded light client could verify ownership of a token or NFT to unlock a bicycle in a rental service, enhancing security and functionality.

Ethereum rollups also benefit from light clients, particularly in safeguarding against hacks on bridge mechanisms used for fund transfers. Light clients embedded in rollups can validate deposits by verifying proofs before releasing tokens, protecting against corrupted data from oracles.

Moreover, upgrading Ethereum wallets with light clients adds a layer of security. Users can ensure their RPC provider's accuracy by directly verifying transaction data, reducing risks associated with erroneous or dishonest data provision.

## Consensus Clients <a href="#consensus-clients" id="consensus-clients"></a>

There are multiple consensus clients (previously known as 'Eth2' clients in the Ethereum network) to support the [consensus upgrades](https://ethereum.org/en/roadmap/beacon-chain/). They are responsible for all consensus-related logic including the fork-choice algorithm, processing attestations and managing block rewards and penalties.

<table data-view="cards"><thead><tr><th>Client</th><th>Language</th><th>Operating systems</th><th>Networks</th><th>Description</th></tr></thead><tbody><tr><td><a href="https://lighthouse.sigmaprime.io/">Lighthouse</a></td><td>Rust</td><td>Linux, Windows, macOS</td><td>Beacon Chain, Goerli, Pyrmont, Sepolia, Ropsten, and more</td><td><p>Lighthouse is a consensus client implementation written in Rust under the Apache-2.0 license. It is maintained by Sigma Prime and has been stable and production-ready since Beacon Chain genesis. It is relied upon by various enterprises, staking pools and individuals. It aims to be secure, performant and interoperable in a wide range of environments, from desktop PCs to sophisticated automated deployments.</p><p>Documentation can be found in <a href="https://lighthouse-book.sigmaprime.io/">Lighthouse Book</a></p></td></tr><tr><td><a href="https://lodestar.chainsafe.io/">Lodestar</a></td><td>TypeScript</td><td>Linux, Windows, macOS</td><td>Beacon Chain, Goerli, Sepolia, Ropsten, and more</td><td><p>Lodestar is a production-ready consensus client implementation written in Typescript under the LGPL-3.0 license. It is maintained by ChainSafe Systems and is the newest of the consensus clients for solo-stakers, developers and researchers. Lodestar consists of a beacon node and validator client powered by JavaScript implementations of Ethereum protocols. Lodestar aims to improve Ethereum usability with light clients, expand accessibility to a larger group of developers and further contribute to ecosystem diversity.</p><p>More information can be found on our <a href="https://lodestar.chainsafe.io/">Lodestar website</a></p></td></tr><tr><td><a href="https://nimbus.team/">Nimbus</a></td><td>Nim</td><td>Linux, Windows, macOS</td><td>Beacon Chain, Goerli, Sepolia, Ropsten, and more</td><td><p>Nimbus is a consensus client implementation written in Nim under the Apache-2.0 license. It is a production-ready client in use by solo-stakers and staking pools. Nimbus is designed for resource efficiency, making it easy to run on resource-restricted devices and enterprise infrastructure with equal ease, without compromising stability or reward performance. A lighter resource footprint means the client has a greater margin of safety when the network is under stress.</p><p>Learn more in <a href="https://nimbus.guide/">Nimbus docs</a></p></td></tr><tr><td><a href="https://docs.prylabs.network/docs/getting-started/">Prysm</a></td><td>Go</td><td>Linux, Windows, macOS</td><td>Beacon Chain, Gnosis, Goerli, Pyrmont, Sepolia, Ropsten, and more</td><td><p>Prysm is a full-featured, open source consensus client written in Go under the GPL-3.0 license. It features an optional webapp UI and prioritizes user experience, documentation, and configurability for both stake-at-home and institutional users.</p><p>Visit <a href="https://docs.prylabs.network/docs/getting-started/">Prysm docs</a> to learn more.</p></td></tr><tr><td><a href="https://consensys.net/knowledge-base/ethereum-2/teku/">Teku</a></td><td>Java</td><td>Linux, Windows, macOS</td><td>Beacon Chain, Gnosis, Goerli, Sepolia, Ropsten, and more</td><td><p>Teku is one of the original Beacon Chain genesis clients. Alongside the usual goals (security, robustness, stability, usability, performance), Teku specifically aims to comply fully with all the various consensus client standards.</p><p>Teku offers very flexible deployment options. The beacon node and validator client can be run together as a single process, which is extremely convenient for solo stakers, or nodes can be run separately for sophisticated staking operations. In addition, Teku is fully interoperable with <a href="https://github.com/ConsenSys/web3signer/">Web3Signer</a> for signing key security and slashing protection.</p><p>Teku is written in Java and is Apache 2.0 licensed. It is developed by the Protocols team at ConsenSys that is also responsible for Besu and Web3Signer. Learn more in <a href="https://docs.teku.consensys.net/en/latest/">Teku docs</a>.</p></td></tr></tbody></table>

### **Optimistic synchronization**

Optimistic synchronization (Optimistic sync) \[more [here](https://github.com/ethereum/consensus-specs/blob/dev/sync/optimistic.md)] is an innovative post-merge synchronization strategy that offers a flexible, opt-in approach for integrating with existing blockchain networks. It is designed to be fully backward compatible, enabling execution clients to synchronize using well-established methods while introducing efficiencies. During this process, the execution engine can optimistically import beacon blocks—blocks from the Beacon Chain, which was part of Ethereum's transition to a proof-of-stake consensus mechanism—without initially verifying each block in detail. This method allows the execution engine to identify the latest head of the chain quickly.

Once the latest head is identified, the execution client can synchronize the chain using traditional methods such as fast or full synchronization. After catching up to the current state of the blockchain, the execution client will confirm the validity of all transactions and the state within the Beacon Chain. At this point, the consensus client manages the consensus protocol operations and is updated on the verified state of transactions, ensuring that all data aligns with the network’s current consensus rules. This strategy not only speeds up the integration and update process for new nodes but also enhances the overall security and robustness of the network by ensuring that all nodes maintain a verified and consistent state without compromising the integrity of the blockchain.

### **Checkpoint synchronization**

Checkpoint synchronization, also called checkpoint sync or weak subjectivity sync \[more [here](https://notes.ethereum.org/@djrtwo/ws-sync-in-practice)], offers an enhanced approach for quickly syncing consensus clients in blockchain networks, particularly useful in networks like Ethereum's Beacon Chain. This method leverages the concept of weak subjectivity, which posits that new checkpoint sync clients can safely synchronize from a recent, trusted checkpoint rather than needing to validate all historical data back to the genesis block. This assumption reduces the synchronization time dramatically, making it more efficient while maintaining trust levels comparable to syncing from the blockchain genesis.

[Weak subjectivity](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/weak-subjectivity/) refers to the reliance on external information—specifically a checkpoint that is generally accepted by the community as valid—to initiate the sync process. In checkpoint sync, a consensus client connects to a trusted remote service to download a snapshot of a recently finalized state of the blockchain. This state includes balances, stakes, and other critical data necessary for the node to function and participate in the network. The node then resumes blockchain verification from this point forward rather than from the beginning.&#x20;

The reliance on a trusted third party to provide this initial state introduces a degree of trust into the process, necessitating careful selection of the data provider to minimize security risks. Providers are generally well-established, highly reputable nodes or services within the community with a proven track record of reliability and integrity. By starting from a recent checkpoint, nodes can rapidly achieve current network state and begin participating in consensus processes, thereby enhancing the scalability and user experience of the blockchain network.

## Further Reading <a href="#further-reading" id="further-reading"></a>

There is a lot of information about Ethereum clients on the internet. Here are few resources that might be helpful.

* [Ethereum 101 - Part 2 - Understanding Nodes](https://kauri.io/ethereum-101-part-2-understanding-nodes/48d5098292fd4f11b251d1b1814f0bba/a) _– Wil Barnes, 13 February 2019_
* [Running Ethereum Full Nodes: A Guide for the Barely Motivated](https://medium.com/@JustinMLeroux/running-ethereum-full-nodes-a-guide-for-the-barely-motivated-a8a13e7a0d31) _– Justin Leroux, 7 November 2019_

## Related Tutorial <a href="#related-tutorials" id="related-tutorials"></a>

* [Turn your Raspberry Pi 4 into a validator node just by flashing the MicroSD card – Installation guide](https://ethereum.org/en/developers/tutorials/run-node-raspberry-pi/) _– Flash your Raspberry Pi 4, plug in an ethernet cable, connect the SSD disk and power up the device to turn the Raspberry Pi 4 into a full Ethereum node running the execution layer (Mainnet) and / or the consensus layer (Beacon Chain / validator)._
