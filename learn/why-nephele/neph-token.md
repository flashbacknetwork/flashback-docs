# Economy Model

<figure><img src="../../.gitbook/assets/Economy_model.png" alt=""><figcaption><p>A high-level representation of the Flashback ecosystem</p></figcaption></figure>

## **Application Layer**

The Flashback platform and its marketplace are the native medium of exchange for transactions in the ecosystem. Consumers pay storage providers to reserve and use storage services in an SLA. The Flashback network platform will provide a marketplace that lists the offers and manages payments.&#x20;

The SLA payments depend on the requested storage, the contract duration, the cloud providers, the redundancy, the QoS level, and other parameters that will be integrated into the SLA. Payment can be made in fiat currency or cryptocurrency.&#x20;

Submitting the SLA requires paying the gas fees related to the smart contract, which will be included in the SLA fees. The SLA fees also include the general fees for the platform running costs and guarantee Flashback operations. Payment in FLASH tokens will enable you to pay reduced SLA fees compared with other currencies.&#x20;

The solutions in the application layer can be subscribed to different tiered levels, which will be defined during the testnet phase. The first Tier is basic storage capacity without paying the SLA fees with minimal functionalities, such as a certain range of providers and solutions. Higher tiers will provide AI-driven tools or more functionalities. &#x20;

The final values will be defined at a later stage of the platform. To resume, the different fees and payments (in fiat or cryptocurrency) from the application layer:

* **SLA Payments for Storage Providers**: Consumers use FLASH to pay storage providers to reserve and utilize storage services under SLAs.  SLA payments vary based on storage amount, contract duration, provider, redundancy, QoS, and other parameters.
* **Platform Operational Fees**: SLA fees, including the smart contract gas fees, also cover platform running costs to sustain Flashback’s operations, such as the marketplace and other advantages related to Flashback.
* **Platform Options**: The platform will offer a unique list of AI-driven tools and solutions to optimize the marketplace for applications and the performance of different providers.
* **Tiered-based plans**: Consumers can select different tiered plans with different options and advantages. The initial plan will offer limited access to the platform, such as a lower priority to commit to SLAs. At the same time, greater tiers will give more flexibility and possibilities with the platform, such as high-priority commitment SLAs and AI-driven tools for pricing and provider selections.&#x20;

#### **Implementation Suggestions for the tokenomics:**

* **Payments:** All payments can be made in tokens.
* **Fees Benefits:** All the fees will receive a large discount if the payment is complete in tokens.
* **Options Benefits:** All the options will receive a large discount if the payment is complete in tokens.
* **Staking:** Consumers can stake tokens to participate in the platform governance and have the following advantages:
  * **Tiered Fee Structure:** Lower fees as transaction volumes or usage milestones are reached (e.g., 1% fee for <100 SLA/month, 0.5% for > 100 transactions/month).
  * **Token Incentives:** Reward transaction fees for active users.
  * **Tiered Plans:** Offer tokens for active users as rewards in the tiered plans.&#x20;
  * **Rewards for Achievements:** By reaching certain milestones and improving the quality of services (providing scoring, etc.), the consumer will receive rewards.
* **Penalties:** Slash the stake or increase fees with the platform or penalties for the unused payment locked in the contract if the consumer does not provide adequate scoring and report with the platform and the smart contracts.

## **Platform and Blockchain Layer**

This layer mainly manages the operations of SLA submissions, arbitrages, and other subtilities. Suppose the application pays in tokens and uses centralized Cloud providers like Amazon (tokenization of Cloud credits). In that case, the platform will then allocate a part of the received funds to a community fund and for decentralized governance. The platform will also optimize the use of smart contracts and the selection fo infrastructure providers.

## **Hardware/Cloud Server Layer**

The platform will directly manage the centralized providers by paying them according to the consumers' needs. Naturally, these providers mainly accept fiat payments, and the platform will manage the payment transmission from the consumers to the provider.

DePin providers like Filecoin, Arweave, or StorJ accept payment in fiat but in their native tokens. Hence, the platform will manage the payment transmission from the consumer to the provider according to the currency the consumer selects.

The infrastructure providers directly connected to the Flashback platform will benefit from its design. According to the currency in the SLA, the platform may participate as an intermediary of payment. Nonetheless, with the proper configuration, the payment in the SLA can be streamed directly to the infrastructure storage provider's wallet. The infrastructure storage provider can pay a subscription to be listed on the platform or stake the platform's native tokens to be authorized for operations.&#x20;

As consumers, storage providers pay the platform to have access to multiple AI-driven tools, which allow them to propose the best pricing according to their hardware and QoS and be competitive against other providers.

Finally, the storage providers will have access to specific tools, such as the compliance system, to refer all the legal documents, geographical locations, eneral performances, etc.

#### **Implementation Suggestions for the tokenomics:**

* **SLA Fees Benefits:** All the fees will receive a large discount if the storage provider pays in tokens.
* **Options Benefits:** All the options will receive a large discount if the payment is complete in tokens.
* **Staking:** Storage providers can stake tokens to be authorized for operations. If the token is staked, then the storage provider can receive the following bonuses:
  * **Risk Offset:** If no penalty is received, the storage provider can receive an offset for providing hardware to support maintenance costs for an initial period.
  * **Token Incentives:** By respecting the QoS proposed in the marketplace, the storage providers may receive an additional bonus in tokens as a percentage of the payments received for SLAs
  * **Rewards for Achievements:** By submitting legal information (registration to the compliance system) or reaching milestones, the storage provider will receive rewards.
* **Penalties:** Slash the stake or increase fees with the platform or lock penalties from the contract's paymentif the provider does not provide an adequate report in the smart contract or does not respect the QoS terms in the SLA.&#x20;



