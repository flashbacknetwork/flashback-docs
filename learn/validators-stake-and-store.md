---
author: Brieuc Berruet <brieuc.berruet@thenephelecloud.com>
---

# Validators: Stake + Store

The proof-of-stake spacetime (PoS-ST) has different responsibilities as validators. Validators are primarily staking-based, equivalent to Ethereum's validators, which are [full nodes](our-network-and-ecosystem/ethereum-stack-in-nephele/basics/nodes-and-clients-1.md). A validator stores data processes transactions and adds new blocks to the blockchain. However, storage duties are limited to on-chain data storage.

The validators can decide to be storage providers by enabling the proof-of-spacetime (PoSt) commitments as validators. This way, you extend your duties with off-chain file storage, the cornerstone of our DePIN-based cloud storage.

## Why be a validator?

### Earn rewards and Be Profitable

Rewards are given for activities that help keep the network secure and running smoothly. You'll earn staking rewards for running Nephele software that groups transactions into new blocks and verifies the work of others. This is essential for maintaining the integrity and security of the chain.

A validator can decide to participate in the file storage duties by allowing the commitment of storage proofs. After setting your parameters and operating fees (what people must pay to store files in your validator), you'll earn rewards according to your performances assessed by the [quality-of-network (QoN) optimizer](quality-of-network-qon-optimizer.md). You will participate in the diversity of storage offers and be a founder of the mass adoption of innovative use cases in the web3 ecosystem. With our novel [proof](consensus-proof-of-stake-spacetime.md), you can also parametrize as you want the storage duties and how you want to commit them to the network. This unique flexibility will allow you to develop a business model with your storage and be competitive. You'll have the best profitability of your storage space.

### Secure the network and Improve the Privacy

The network becomes more secure against attacks as more NEPH is staked. This is because controlling most of the network would require owning the most staked NEPH. Essentially, the more NEPH staked, the harder it is for anyone to gain enough control to pose a threat. You will be a cornerstone of the security and decentralization of the network.

If you enable file storage, you can participate in the cloud storage layer and improve the network's security, privacy, and value. You will be the precursor of a fairer and competitive world where every individual and business can store their files according to their requirements.

### Participate in a Sustainable Ecosystem

Doing staking is the best way to consume limited resources, the opposite of the proof-of-work or proof-of-capacity-based systems. This is why Nephele used the staking model to avoid a frantic race for the power of block validation.

Nephele chose to develop a sustainable ecosystem by design. You'll be part of decision processes toward greener and more sustainable cloud storage by offering and optimizing our operating fees depending on your energy consumption, workforce, and other criteria.

## How to become a Validator?

There are 3 different ways to become a validator:

* **Solo Validator**: This is the ultimate standard. You have full participation rewards, you improve the decentralization of the network, and you never require trusting anyone else with your funds. You'll need a dedicated computer connected to the Internet. This connection must be stable and available \~24/7.



### What are the benefits to run a node? <a href="#why-should-i-run-an-ethereum-node" id="why-should-i-run-an-ethereum-node"></a>

Running a node allows you to directly, trustlessly, and privately use Nephele while supporting the network by keeping it more robust and decentralized. A node is the cornerstone of our techology but the gateway for services and applications to the network and its protocol.&#x20;

#### Contribute, build, and earn as a node operator <a href="#benefits-to-you" id="benefits-to-you"></a>

Operating a personal node on the Nephele network facilitates the utilization of the system in a manner that is both private and self-reliant, eliminating the necessity for external trust. This approach aligns with the decentralized ethos prevalent within blockchain technology, encapsulated by the adage "Don't trust, verify."&#x20;

This principle underscores the ability of individuals to independently verify the authenticity and accuracy of data through their own client, thereby circumventing reliance on third-party verifications that might otherwise compromise the integrity and security of the transactions. This method enhances the robustness of the network by promoting a trustless environment where each node contributes to the overall transparency and reliability of the system.

* Your node verifies all the transactions and blocks against consensus rules by itself. This means you don’t have to rely on or fully trust any other nodes in the network.
* You can use an Ethereum wallet with your node (Nephele is EVM-compatible). You can use dapps more securely and privately because you won't have to leak your addresses and balances to intermediaries. Everything can be checked with your client. [MetaMask](https://metamask.io/), [Frame](https://frame.sh/), and [many other wallets](https://ethereum.org/en/wallets/find-wallet/) offer RPC importing, allowing them to use your node.
* You can run and self-host other services that depend on data from Nephele. For example, this might be software like layer 2, infrastructure, block explorers, payment processors, etc., for the blockchain operations. You will be also to deploy your self-hosted services and applications for the d
* You can provide your own custom [RPC endpoints](https://ethereum.org/en/developers/docs/apis/json-rpc/). You could even offer these endpoints publicly to the community to help them avoid big centralized providers.
* You can connect to your node using i**nter-process communications (IPC)** or rewrite the node to load your program as a plugin. This grants low latency, which helps a lot, e.g. when processing a lot of data using web3 libraries or when you need to replace your transactions as fast as possible (i.e. frontrunning).
* You can directly earn NEPH to secure the network and earn rewards by validating blocks (staking) and storing files for services and applications. See [Validators: Stake + Store](validators-stake-and-store.md) to know more.

<figure><img src="https://ethereum.org/_next/image/?url=%2Fcontent%2Fdevelopers%2Fdocs%2Fnodes-and-clients%2Fnodes.png&#x26;w=1920&#x26;q=75" alt=""><figcaption></figcaption></figure>

#### Network benefits <a href="#network-benefits" id="network-benefits"></a>

A diverse set of nodes is important for Nephele's health, security and operational resiliency.

* Full nodes enforce the consensus rules so they can’t be tricked into accepting blocks that don't follow them. This provides extra security in the network because if all the nodes were light nodes, which don't do full verification, validators could attack the network.
* In an attack that overcomes the crypto-economic defenses of [proof-of-stake](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/#what-is-pos), a social recovery can be performed by full nodes following the honest chain.
* More nodes in the network result in a more diverse and robust network, the ultimate goal of decentralization, which enables a censorship-resistant and reliable system.
* Full nodes provide lightweight clients with access to blockchain data. Light nodes don't store the whole blockchain. Instead, they verify data via the [state roots in block headers](https://ethereum.org/en/developers/docs/blocks/#block-anatomy). They can request more information from full nodes if they need it.
* nother benefit that does not exist in Ethereum is that your full node will allow you to participate to the decentralized data storage of Nephele. You will ensure more security and privacy for individuals' and businesses' data, and you will be an actor of the data freedom we are lacking of.&#x20;
