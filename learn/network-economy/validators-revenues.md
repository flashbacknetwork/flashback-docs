# Validators' Revenues

## Staking Revenues

In the Flashback network, validators play a critical role in maintaining the network's integrity, security, and functionality. The revenue model for validators in Flashback, who stake their FLASH tokens to participate in network consensus, includes several sources of income.

### **Block rewards**

* **Primary Income**: Validators earn block rewards for proposing and validating new blocks. These rewards are issued in FLASH and are designed to compensate validators for their computational efforts, energy costs, and the capital locked up as stake.
* **Reward Mechanism**: The Flashback network periodically mints new FLASH tokens as part of its inflationary policy, which are distributed to validators as block rewards. The rate of these rewards may decrease over time as the network reaches certain milestones or the total supply caps.

### **Transaction fees**

* **Direct Transaction Costs**: Validators receive transaction fees from users executing transactions, such as token transfers or smart contract interactions. Users pay these fees to compensate validators for the computational resources required to process and include transactions in a block.
* **Dynamic Fee Structure**: The fee per transaction can vary based on network congestion and transaction complexity, providing an additional incentive for validators during periods of high demand.

### **Network-specific fees**

* **Special Operations**: Besides regular transactions, validators may earn fees from specific network functions such as executing large-scale smart contracts, participating in network upgrades, or managing cross-chain operations if Flashback supports interoperability features.

### **MEV (Miner Extractable Value)**

* **Additional Earnings**: Validators in Flashback can earn from MEV, which refers to the profit a validator can make through their ability to arbitrarily include, exclude, or reorder transactions within the blocks they produce. This might involve strategies like front-running large trades or maximizing arbitrage opportunities between decentralized finance (DeFi) protocols.
* **Ethical Considerations and Risks**: While MEV can significantly increase validator revenues, it also introduces risks and ethical considerations, potentially impacting network fairness and stability.

### Passive incomes and delegation

* **Passive Income**: Apart from actively validating blocks, validators earn staking rewards simply for participating in the consensus mechanism by locking their FLASH tokens. This secures the network by ensuring a sufficient token supply is staked, reducing liquidity and limiting circulating supply, which can also stabilize the token’s value.
* **Delegation Systems**: If Flashback implements a delegation system, validators can also earn additional fees by accepting delegated stakes from other token holders who wish to participate in the staking process without running a validator node themselves.

***

## Storage Revenues

Flashback leverages decentralized storage solutions like the one facilitated by the Quality-of-Network (QoN) Optimizer, validators play a crucial role in maintaining data availability and integrity. Their revenue model is fundamental to incentivize participation and ensure the network remains robust and reliable. Here’s a detailed overview of how validators generate revenue from their storage operations within such a system:

### **Data Storage Fees**

* **Primary Revenue Source**: Validators charge fees for storing data on behalf of users. These fees are typically set based on the amount of data stored, the duration of storage, and the required accessibility or bandwidth.
* **Contract-Based Pricing**: In systems like the QoN Optimizer, storage fees might be predefined in smart contracts, which specify the terms and conditions for storing and accessing data.
* **Dynamic Pricing Models**: Fees can vary based on the urgency of access, the popularity of the data, or market dynamics, allowing validators to capitalize on high-demand data assets.

### **Performance-Based Incentives**

* **Efficiency Rewards**: Validators can earn additional payments for superior performance, particularly for meeting or exceeding service level agreements regarding data retrieval times. For instance, the QoN Optimizer rewards validators who consistently provide the quickest average response times to data requests.
* **Penalties for Poor Performance**: Conversely, slower response times or failures to meet the agreed performance metrics can result in penalties, reducing the potential earnings or even leading to financial losses due to slashed collateral.

### **Rebates and Bonuses**

* **Contract Completion Bonuses**: Upon successfully completing a storage contract, validators may receive bonuses, especially if they have maintained excellent performance throughout the contract period.
* **Rebates for Efficiency**: In systems like the QoN Optimizer, a portion of the fees collected from all validators may be redistributed as rebates to those who demonstrate top efficiency and reliability, providing a competitive advantage.

***

## Case Studies of Storage Provision

Making deals requires you to select the different validators you want to operate in your service. Specifically, Flashback will have a on-chain marketplace that refers to all the nodes and their pricing. However, it can be complex to estimate its storage cost as a physical storage infrastructure provider. The following example illustrates approaches which can help you to understand how you can set your price. The figures provided are illustrative to support understanding, and should be aligned with actual deployment costs. We assume a staking of 10,000 FLASH staked per node and a circulating supply of 1,000,000,000 FLASH.&#x20;

A recommended configuration when you have a lot of TB is to add a GPU-based server that takes charge of the proof computation. Another option is to use a service called Sealing-as-a-Service (SlaaS) that will take charge of the proof computation. Using a GPU or a SlaaS speeds the storage availability in nodes. However, this kind of service is new and it isn't easy to find public data. We’ll then only assume configuration with a GPU. We assume that the storage provider wants to make 50% of benefits on the costs.We also set a minimal operating fee of 0.25 USD/TB/Month.

Disclaimer: The following configurations come from the same provider and are just here to give insights to our reader.

| Storage Server             | STANDARD                                  | LARGE                                         | HIGH-GRADE                               |
| -------------------------- | ----------------------------------------- | --------------------------------------------- | ---------------------------------------- |
| Price                      | 100 USD/Month                             | 700 USD/Month                                 | 2,400 USD/Month                          |
| Storage                    | 24 TB of HDD SATA                         | 112 TB of HDD SAS                             | 92 TB of SSD NVMe                        |
| Processor (CPU)            | Intel Xeon-D 1521 - 4c/8t - 2.4GHz/2.7GHz | AMD Ryzen 7 Pro 3700 - 8c/16t - 3.6GHz/4.4GHz | AMD Epyc 7402 - 24c/48t - 2.8GHz/3.35GHz |
| Memory (RAM)               | 16GB DDR4 ECC 2133MHz                     | 64GB DDR4 ECC 2933MHz                         | 750GB DDR4 ECC 2933MHz                   |
| Bandwidth (Public/Private) | <p>500 MB/s</p><p> 1 GB/s</p>             | <p>3 GB/s</p><p>6 GB/s</p>                    | <p>10 GB/s</p><p>25 GB/s</p>             |

An assumption is that this GPU configuration is limited by the private bandwidth with storage nodes. Let’s now consider 3 different configurations (no mixing server type to keep winning rate constant) with the proof computation limitation:

| Configurations             | CONF-1            | CONF-2          | CONF-3           |
| -------------------------- | ----------------- | --------------- | ---------------- |
| Price                      | 3,450 USD/Month   | 3,750 USD/Month | 3,350 USD/Month  |
| Composition                | 25 STANDARD       | 4 ADVANCE       | 1 HIGH-GRADE     |
| Estimated centralized fees | 12.5 USD/TB/Month | 23 USD/TB/Month | 100 USD/TB/Month |
| GPU                        | Yes               | Yes             | Yes              |
| Winning rate\* (QoN)       | 50%               | 75%             | 100%             |

\*Assumptions based on a future expectation of the network’s quality.

### Case 1: Early stage of the network

* 2.5% of the network is staked = 2,500 nodes in the network.
* Staking APY of nodes: 327%
* Network valuation: $100m (1 FLASH = 0.1 USD)

In this situation, one node provides 32,700 tokens i.e. 3,270 USD in 1 year. Here is the operating fees according to our assumptions:

| Configurations          | CONF-1            | CONF-2          | CONF-3            |
| ----------------------- | ----------------- | --------------- | ----------------- |
| Monthly staking Rewards | 68,125 FLASH      | 10,900 FLASH    | 2,725 FLASH       |
| Monthly staking incomes | 6,812 USD         | 1,090 USD       | 272 USD           |
| Missing benefits        | 0 USD             | 4,535 USD       | 4,825 USD         |
| Operating fees          | 0.25 USD/TB/Month | 13 USD/TB/Month | 51.6 USD/TB/Month |
| Discount                | -98%              | -43.5%          | -48.4%            |

### Case 2: Growth of the staking profits

* 5% of the network is staked = 5,000 nodes in the network.
* Staking APY of nodes: 115%
* Network valuation: $500m (1 token = 0.5 USD)

In this situation, one node provides 11,500 tokens i.e. 5,750 USD in 1 year. Here is the operating fees according to our assumptions:

| Configurations          | CONF-1            | CONF-2             | CONF-3            |
| ----------------------- | ----------------- | ------------------ | ----------------- |
| Monthly staking Rewards | 23,960 tokens     | 3,834 tokens       | 960 tokens        |
| Monthly staking incomes | 11,980 USD        | 1,916 USD          | 480 USD           |
| Missing benefits        | 0 USD             | 3,709 USD          | 4,545 USD         |
| Operating fees          | 0.25 USD/TB/Month | 11.03 USD/TB/Month | 47.3 USD/TB/Month |
| Discount                | -98%              | -52.04%            | -52.7%            |

### Case 3: Weak network growth while drop in staking rewards

* 20% of the network is staked = 20,000 nodes in the network.
* Staking APY of nodes: 14%
* Network valuation: $1b (1 token = 1 USD)

In this situation, one node provides 1,400 tokens i.e. 1,400 USD in 1 year. Here is the operating fees according to our assumptions:

| Configurations                             | CONF-1            | CONF-2            | CONF-3             |
| ------------------------------------------ | ----------------- | ----------------- | ------------------ |
| Monthly staking Rewards                    | 2,915 tokens      | 465 tokens        | 115 tokens         |
| Monthly staking incomes                    | 2,915 USD         | 465 USD           | 115 USD            |
| Missing benefits                           | 2,260 USD         | 5,160 USD         | 4,545 USD          |
| Operating fees                             | 7.53 USD/TB/Month | 15.4 USD/TB/Month | 53.37 USD/TB/Month |
| Discount compared to centralized solutions | -39.76%           | -33.04%           | -46.63%            |

### Case 4: Extremely strong network growth while drop in staking rewards

* 20% of the network is staked = 20,000 nodes in the network.
* Staking APY of nodes: 14%
* Network valuation: $25b (1 token = 25 USD)

In this situation, one node provides 1,400 tokens i.e. 35,000 USD in 1 year. Here is the operating fees according to our assumptions:

| Configurations                             | CONF-1            | CONF-2            | CONF-3             |
| ------------------------------------------ | ----------------- | ----------------- | ------------------ |
| Monthly staking Rewards                    | 2,915 tokens      | 465 tokens        | 115 tokens         |
| Monthly staking incomes                    | 72,915 USD        | 11,665 USD        | 2,915 USD          |
| Missing benefits                           | 0 USD             | 0 USD             | 2,110 USD          |
| Operating fees                             | 0.25 USD/TB/Month | 0.25 USD/TB/Month | 22.93 USD/TB/Month |
| Discount compared to centralized solutions | -98%              | -99.04%           | -87.03%            |

### Conclusion

The operating fee is a decision of the storage provider. This section is to illustrate an operator's strategy for deciding the operating fees. Storage providers must consider other hardware such as SSD, NVMe, etc. Low operating fees do not mean storage priority. It is just a market offer and users will choose what is convenient for them and their use cases.

***

## Governance and Long-Term Financial Incentives

### **Governance Participation**

* **Decision-Making Influence**: Validators play a crucial role in the governance of the Flashback network. Although this does not directly translate into immediate financial gains, it empowers validators with significant influence over key decisions that shape the network's future. This includes changes in tokenomics, operational rules, and the overall strategic direction, which can indirectly affect their potential earnings and operational efficiency.

### **Long-Term Financial Incentives**

* **Price Appreciation**: By participating in the staking process, validators benefit financially from the appreciation of the FLASH tokens. As the network expands and demand for FLASH increases, the value of their staked holdings is likely to rise, offering substantial economic benefits over time.
* **Collateral Returns and Interest**: Validators who are required to post collateral might earn interest on these deposits. Furthermore, they stand to gain from the appreciation in the value of these locked tokens or assets, providing an additional layer of financial return on their investments.
