# Nodes

A "node" is a computer connected to other computers, forming a peer-to-peer network. A node has to run two clients: a [consensus client](nodes-and-clients.md#consensus-clients) and an [execution client](nodes-and-clients.md#execution-clients).

### NODE TYPES <a href="#node-types" id="node-types"></a>

If you want to [run your own node](https://ethereum.org/en/developers/docs/nodes-and-clients/run-a-node/), you should understand that there are different types of node that consume data differently. In fact, clients can run three different types of nodes: light, full and archive. There are also options of different sync strategies which enable faster synchronization time. Synchronization refers to how quickly it can get the most up-to-date information on Ethereum's state.

#### Full node <a href="#full-node" id="full-node"></a>

Full nodes do a block-by-block validation of the blockchain, including downloading and verifying the block body and state data for each block. There are different classes of full node - some start from the genesis block and verify every single block in the entire history of the blockchain. Others start their verification at a more recent block that they trust to be valid (e.g. Geth's 'snap sync'). Regardless of where the verification starts, full nodes only keep a local copy of relatively recent data (typically the most recent 128 blocks), allowing older data to be deleted to save disk space. Older data can be regenerated when it is needed.

* Stores full blockchain data (although this is periodically pruned so a full node does not store all state data back to genesis)
* Participates in block validation, verifies all blocks and states.
* All states can be either retrieved from local storage or regenerated from 'snapshots' by a full node.
* Serves the network and provides data on request.

#### Archive node <a href="#archive-node" id="archive-node"></a>

Archive nodes are full nodes that verify every block from genesis and never delete any of the downloaded data.

* Stores everything kept in the full node and builds an archive of historical states. It is needed if you want to query something like an account balance at block #4,000,000, or simply and reliably test your own transactions set without mining them using tracing.
* This data represents units of terabytes, which makes archive nodes less attractive for average users but can be handy for services like block explorers, wallet vendors, and chain analytics.

Syncing clients in any mode other than archive will result in pruned blockchain data. This means, there is no archive of all historical states but the full node is able to build them on demand.

Learn more about [Archive nodes](https://ethereum.org/en/developers/docs/nodes-and-clients/archive-nodes/).

#### Light node <a href="#light-node" id="light-node"></a>

Instead of downloading every block, light nodes only download block headers. These headers contain summary information about the contents of the blocks. Any other information the light node requires gets requested from a full node. The light node can then independently verify the data they receive against the state roots in the block headers. Light nodes enable users to participate in the Ethereum network without the powerful hardware or high bandwidth required to run full nodes. Eventually, light nodes might run on mobile phones or embedded devices. The light nodes do not participate in consensus (i.e. they cannot be miners/validators), but they can access the Ethereum blockchain with the same functionality and security guarantees as a full node.

Light clients are an area of active development for Ethereum and we expect to see new light clients for the consensus layer and execution layer soon. There are also potential routes to providing light client data over the [gossip network(opens in a new tab)](https://www.ethportal.net/). This is advantageous because the gossip network could support a network of light nodes without requiring full nodes to serve requests.

Ethereum does not support a large population of light nodes yet, but light node support is an area expected to develop rapidly in the near future. In particular, clients like [Nimbus(opens in a new tab)](https://nimbus.team/), [Helios(opens in a new tab)](https://github.com/a16z/helios), and [LodeStar(opens in a new tab)](https://lodestar.chainsafe.io/) are currently heavily focused on light nodes.

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

