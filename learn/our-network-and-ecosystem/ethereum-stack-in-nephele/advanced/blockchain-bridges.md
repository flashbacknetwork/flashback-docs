# Blockchain Bridges

With the proliferation of L1 blockchains and L2 [scaling](https://ethereum.org/en/developers/docs/scaling/) solutions, alongside an ever-growing number of decentralized applications going cross-chain, the need for communication and asset movement across chains has become an essential part of network infrastructure. Different types of bridges exist to help make this possible.

## What is a (blockchain) bridge? <a href="#need-for-bridges" id="need-for-bridges"></a>

Bridges are crucial tools that enable different blockchain networks to communicate and interact. Typically, blockchains operate in isolation, which means they can't naturally exchange or transfer data, tokens, or smart contract calls with other blockchains. This isolation can limit the growth and innovation within a blockchain ecosystem by restricting its ability to interact with other ecosystems.

Bridges solves this problem by creating a link between separate blockchain networks, allowing for transferring tokens, messages, data, and even [smart contract](../basics/smart-contracts.md) instructions across these networks. Essentially, they build a conduit for communication and transaction between disparate blockchain systems, enhancing connectivity and interoperability.

Bridges significantly enhance the functionality of blockchain networks by facilitating the exchange of data and assets between them. Each blockchain has its own strengths and weaknesses, along with distinct features that dictate how applications are built, including aspects like transaction speed, capacity, and cost. Bridges contribute to the development of the broader cryptocurrency ecosystem by allowing these networks to utilize each other's innovations.

For developers, bridges offer several advantages:

* They allow the seamless transfer of data, information, and assets across different blockchain networks.
* They enable the development of new features and use cases for protocols by expanding the range of possibilities for what these protocols can achieve. For instance, a yield farming protocol that operates on the Ethereum Mainnet could be expanded to include liquidity pools on all EVM-compatible chains.
* They allow developers to harness the benefits of various blockchains, such as using lower-cost Layer 2 solutions like rollups and sidechains for deploying decentralized applications (dapps), while allowing users to bridge across these platforms.
* They foster collaboration among developers from different blockchain ecosystems, encouraging them to create innovative products together.
* They help attract a diverse range of users and communities to their dapps, expanding their user base and enhancing network effects.

## Approach and classification <a href="#how-do-bridges-work" id="how-do-bridges-work"></a>

While there are many [types of bridge designs](https://li.fi/knowledge-hub/blockchain-bridges-and-classification/), three ways to facilitate the cross-chain transfer of assets stand out:

* **Lock and mint –** Lock assets on the source chain and mint assets on the destination chain.
* **Burn and mint –** Burn assets on the source chain and mint assets on the destination chain.
* **Atomic swaps –** Swap assets on the source chain for assets on the destination chain with another party.

Bridges can usually be classified into one of the following buckets:

* **Native bridges –** These bridges are typically built to bootstrap liquidity on a particular blockchain, making it easier for users to move funds to the ecosystem. Example: [Arbitrum Bridge](https://bridge.arbitrum.io/), [Polygon Portal](https://portal.polygon.technology/), [Optimism Gateway](https://app.optimism.io/bridge).
* **Validator or oracle-based bridges –** These bridges rely on an external validator set or oracles to validate cross-chain transfers. Examples: Multichain and Across.
* **Generalized message passing bridges –** These bridges can transfer assets, messages, and arbitrary data across chains. Examples: Axelar, LayerZero, and Nomad.
* **Liquidity networks –** These bridges primarily focus on transferring assets from one chain to another via atomic swaps. Generally, they don’t support cross-chain message passing. Examples: Connext and Hop.

## Pros and Cons <a href="#trade-offs" id="trade-offs"></a>

Bridges in blockchain technology offer distinct advantages and disadvantages based on their design and implementation. Here's a breakdown of these factors in a pros and cons manner for both trusted and trustless bridges:

### Trusted Bridges

**Pros:**

* **High Connectivity:** Trusted bridges typically provide excellent connectivity, enabling them to connect a wide range of blockchains including rollups, sidechains, and other layer 1 blockchains.
* **Speed and Cost-Effectiveness:** These bridges often perform well in terms of transaction speed and cost-efficiency, making them attractive for users needing quick and economical transfers.
* **Complex Data Transfer:** They are capable of enabling fully generalized message passing, which allows for the transfer of complex data and messages across chains.

**Cons:**

* **Security Concerns:** Security is a significant drawback as these rely on external validators. Users must trust the security measures of the bridge rather than the blockchain’s native security protocols.
* **Integration Complexity:** Depending on the bridge, integration might be complex and require significant developer effort.

### Trustless Bridges

**Pros:**

* **Enhanced Security:** Trustless bridges are considered more secure because they rely on the native validators of the blockchains they connect. They do not introduce new trust assumptions beyond those inherent to the connected blockchains.
* **No External Validators:** These bridges do not depend on external parties for validation, relying instead on the underlying blockchain's security mechanisms.

**Cons:**

* **Limited Data Transfer:** Most trustless bridges, especially liquidity networks, do not support the passing of complex data beyond basic asset transfers.
* **Variable Connectivity and Speed:** The connectivity and speed of trustless bridges can vary. For example, light client bridges may face connectivity limitations, and optimistic bridges might experience delays due to their reliance on fraud proofs for security.

### **Specific Types of Trustless Bridges**

* **Generalized Message Passing Bridges:**
  * **Pros:** Good security and capable of transferring complex data. Often cost-effective.
  * **Cons:** May suffer from connectivity issues and slower speeds due to the robust security measures like fraud proofs.
* **Liquidity Networks:**
  * **Pros:** Typically provide excellent security and speed. They are also considered cost-effective and offer good connectivity.
  * **Cons:** Unable to handle complex data transfer which limits their use in applications needing generalized message passing.

When evaluating bridges, developers and users must consider their specific needs for security, cost, speed, connectivity, and the complexity of the data to be transferred. The choice between a trusted and a trustless bridge will largely depend on the user's security requirements and the type of operations they intend to perform across blockchains.

## A reminder of risks with bridges <a href="#risk-with-bridges" id="risk-with-bridges"></a>

Bridges account for the top three [biggest hacks in DeFi](https://rekt.news/leaderboard/) and are still in the early stages of development. Using any bridge carries the following risks:

* **Smart contract risk –** While many bridges have successfully passed audits, all it takes is one flaw in a smart contract for assets to be exposed to hacks (ex: [Solana’s Wormhole Bridge](https://rekt.news/wormhole-rekt/)).
* **Systemic financial risks** – Many bridges use wrapped assets to mint canonical versions of the original asset on a new chain. This exposes the ecosystem to systemic risk, as wrapped versions of tokens are exploited.
* **Counterparty risk –** Some bridges utilize a trusted design that requires users to rely on the assumption that validators will not collude to steal user funds. The need for users to trust these third-party actors exposes them to risks such as rug pulls, censorship, and other malicious activities.
* **Open issues –** Given that bridges are in the nascent stages of development, there are many unanswered questions related to how bridges will perform in different market conditions, like times of network congestion and during unforeseen events such as network-level attacks or state rollbacks. This uncertainty poses certain risks, the degree of which is still unknown.

## DApps with Bridges <a href="#how-can-dapps-use-bridges" id="how-can-dapps-use-bridges"></a>

Here are some practical applications that developers can consider about bridges and taking their dapp cross-chain:

### Integrating bridges <a href="#integrating-bridges" id="integrating-bridges"></a>

For developers, there are many ways to add support for bridges:

1. **Building your own bridge –** Building a secure and reliable bridge is not easy, especially if you take a more trust-minimized route. Moreover, it requires years of experience and technical expertise related to scalability and interoperability studies. Additionally, it would require a hands-on team to maintain a bridge and attract sufficient liquidity to make it feasible.
2. **Showing users multiple bridge options –** Many [dapps](https://ethereum.org/en/developers/docs/dapps/) require users to have their native token to interact with them. To enable users to access their tokens, they offer different bridge options on their website. However, this method is a quick fix to the problem as it takes the user away from the dapp interface and still requires them to interact with other dapps and bridges. This is a cumbersome onboarding experience with the increased scope of making mistakes.
3. **Integrating a bridge –** This solution doesn’t require the dapp to send users to the external bridge and DEX interfaces. It allows dapps to improve the user onboarding experience. However, this approach has its limitations:
   * Assessment and maintenance of bridges are hard and time-consuming.
   * Selecting one bridge creates a single point of failure and dependency.
   * The dapp is limited by the bridge’s capabilities.
   * Bridges alone might not be enough. Dapps might need DEXs to offer more functionality such as cross-chain swaps.
4. **Integrating multiple bridges –** This solution solves many problems associated with integrating a single bridge. However, it also has limitations, as integrating multiple bridges is resource-consuming and creates technical and communication overheads for developers—the scarcest resource in crypto.
5. **Integrating a bridge aggregator –** Another option for dapps is integrating a bridge aggregation solution that gives them access to multiple bridges. Bridge aggregators inherit the strengths of all the bridges and thus are not limited by any single bridge’s capabilities. Notably, the bridge aggregators typically maintain the bridge integrations, which saves the dapp from the hassle of staying on top of the technical and operational aspects of a bridge integration.

That being said, bridge aggregators also have their limitations. For instance, while they can offer more bridge options, many more bridges are typically available in the market than those offered on the aggregator's platform. Moreover, like bridges, bridge aggregators are exposed to smart contract and technology risks (more smart contracts = more risks).

If a dapp goes down the route of integrating a bridge or an aggregator, there are different options based on how deep the integration is meant to be. For instance, if it’s only a front-end integration to improve the user onboarding experience, a dapp would integrate the widget. However, if the integration is to explore deeper cross-chain strategies like staking, yield farming, etc., the dapp integrates the SDK or API.

### Deploying a dapp on multiple chains <a href="#deploying-a-dapp-on-multiple-chains" id="deploying-a-dapp-on-multiple-chains"></a>

To deploy a dapp on multiple chains, developers can use development platforms like [Alchemy](https://www.alchemy.com/), [Hardhat](https://hardhat.org/), [Truffle](https://trufflesuite.com/), [Moralis](https://moralis.io/), etc. Typically, these platforms come with composable plugins that can enable dapps to go cross-chain. For instance, developers can use a deterministic deployment proxy offered by the [hardhat-deploy plugin](https://github.com/wighawag/hardhat-deploy).

**Examples:**

* [How to build cross-chain dapps](https://moralis.io/how-to-build-cross-chain-dapps/)
* [Building a Cross-Chain NFT Marketplace](https://youtu.be/WZWCzsB1xUE)
* [Moralis: Building cross-chain NFT dapps](https://www.youtube.com/watch?v=ehv70kE1QYo)

### Monitoring contract activity across chains <a href="#monitoring-contract-activity-across-chains" id="monitoring-contract-activity-across-chains"></a>

To monitor contract activity across chains, developers can use subgraphs and developer platforms like Tenderly to observe smart contracts in real-time. Such platforms also have tools that offer greater data monitoring functionality for cross-chain activities, such as checking for [events emitted by contracts(opens in a new tab)](https://docs.soliditylang.org/en/v0.8.14/contracts.html?highlight=events#events), etc.

**Tools**

* [The Graph](https://thegraph.com/en/)
* [Tenderly](https://tenderly.co/)

## Further Reading <a href="#further-reading" id="further-reading"></a>

* [Blockchain Bridges: Building Networks of Cryptonetworks](https://medium.com/1kxnetwork/blockchain-bridges-5db6afac44f8) Sep 8, 2021 – Dmitriy Berenzon
* [The Interoperability Trilemma](https://blog.connext.network/the-interoperability-trilemma-657c2cf69f17) Oct 1, 2021 – Arjun Bhuptani
* [Clusters: How Trusted & Trust-Minimized Bridges Shape the Multi-Chain Landscape](https://blog.celestia.org/clusters/) Oct 4, 2021 – Mustafa Al-Bassam
* [LI.FI: With Bridges, Trust is a Spectrum](https://blog.li.fi/li-fi-with-bridges-trust-is-a-spectrum-354cd5a1a6d8) Apr 28, 2022 – Arjun Chand

Additionally, here are some insightful presentations by [James Prestwich](https://twitter.com/\_prestwich) that can help develop a deeper understanding of bridges:

* [Building Bridges, Not Walled Gardens](https://youtu.be/ZQJWMiX4hT0)
* [Breaking Down Bridges](https://youtu.be/b0mC-ZqN8Oo)
* [Why are the Bridges Burning](https://youtu.be/c7cm2kd20j8)
