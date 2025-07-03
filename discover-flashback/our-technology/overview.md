# Overview

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (23).jpg" alt=""><figcaption><p>Quick Overview of the interactions between Flashback DePin, providers, and consumers</p></figcaption></figure>

The rise of Web3 technologies has led to the emergence of innovative concepts that challenge traditional models. Decentralized networks have paved the way for new solutions, offering greater transparency, security, and efficiency.

**Flashback DePin** is designed as a decentralized, trust-enforced system that connects **Consumers** and **Providers** while maintaining **transparency through smart contracts and its network**. The smart contract ensures compliance, streamlines data and payment flows, while Flashback DePin platform enhances discoverability, trust, and accountability, supporting a reliable decentralized storage ecosystem.

***

## **Flashback DePin: A decentralized platform**

The Flashback DePin manages key operations, including service-level agreement (SLA) submissions, arbitration, and other advanced tools in the future to support an optimal user experience.

To ensure flexibility, the solution supports both fiat and cryptocurrency payments (BTC, XLM, STRK, ALGO, and others) for services. The solution also offers Providers the freedom to choose from multiple blockchain networks that will support our smart contract. For instance, if the user is part of an ecosystem, they will be able to connect their ecosystem wallet and pay in tokens from this ecosystem. Meanwhile, the platform will handle payments and currency conversion until decentralized swap functions are integrated.

**Smart Contract Orchestrators**

Orchestrators communicate through **Flashback DePin**, ensuring that SLAs, payments, and quality metrics are synchronized and enforced.

* **Orchestrator for Providers**: Manages agreements, service-level parameters, and quality monitoring for Providers.
* **Orchestrator for Consumers**: Handles payments, data access permissions, and SLA terms to ensure fair usage.

**Flashback DePin's Core Functions**

The core of the platform is where Flashback Inc. will run its main operations. It will integrate different layers of stacks and tools to guarantee a seamless and user-friendly integration into the applications and services of the consumers.

* **Monitor:** The platform will have a monitoring function that will monitor the performance of the Providers and Data Units.&#x20;
* **Register:** A database within the Flashback DePin platform that lists Providers and Consumers meeting certification requirements. Certification ensures Providers meet quality-of-service (QoS) standards and can be trusted for SLAs and vice versa with certified Consumers.&#x20;
* **Marketplace**: Acts as a public interface where Providers are listed for Consumers to browse and choose from. Facilitates discovery and selection while maintaining transparency about certifications and performance ratings.
* **Oracles**: A decentralized network of SLA validators to support the reports from Consumers and Providers. While the first iterations of the Flashback DePin platform will support this assessment internally, the platform will offer to certified validators the capacity to report the SLAs and QoS Metrics to the smart contracts.&#x20;

***

## **Consumers (or Unit Consumers)**

* Represent individuals, organizations, or applications requiring storage or compute solutions.&#x20;
* Interact with providers via the Flashback DePin platform, its oracle network, and smart contract orchestrators to store, retrieve, or manage their data.

The SLA payments depend on the requested storage and/or compute, the contract duration, the Providers, the redundancy, the QoS level, and other parameters that will be integrated into the SLA. Payment can be made in fiat currency or cryptocurrency.&#x20;

***

## **Providers (or Unit Providers)**

The Providers with storage and/or compute infrastructure directly connected to the platform will benefit from its design. Concerning the payment, it can be streamed directly to the Provider's wallet but the platform may play a key role as an oracle to measure the performances of the Provider with the Consumers. The provider can pay a subscription to be listed on the platform and to stake the native tokens to be authorized for operations.&#x20;

* Entities offering storage and/or compute infrastructure by submitting storage or compute units in the marketplace or to accept a storage or compute requests from Consumers.&#x20;
* Responsible for offering storage capacity to consumers and must meet the platform’s quality standards or consumers' requirements.&#x20;
* Registered and certified within the platform for trust and compliance.

### Bridge Node

The Bridge Node will play an essential role in our infrastructure. Indeed, this proprietary technology will enable Providers to:

* Manage data transfer between Consumer and Provider thanks to S3 and GCS compatibility.
* Provide performance reports to Oracles, which will submit the metrics to the smart contracts.

After installing the Bridge Node in its infrastructure via the Flashback DePin platform, the Provider can reference its Bridge Node by submitting the necessary information to the smart contracts via the APIs or the platform interface. The Provider can then submit its Data Units.

The procedure for installing a Bridge Node is as follows:

* The Provider installs locally the Bridge Node. Once installed, a notification is sent to the Flashback DePin Platform to be actively listed there and it generates a secret key sent to the Provider in the console.
* The Provider connects its wallet the platform and search the Bridge Node. Hence, the Provider claims the Bridge Node which provides a code to give to the Bridge Node locally. This operation will authorize the wallet to send the collateral.&#x20;
* On the platform, you can find the Bridge Node in your personal list related to your wallet, you can then send the collateral and start to create your Data Units.&#x20;

\
