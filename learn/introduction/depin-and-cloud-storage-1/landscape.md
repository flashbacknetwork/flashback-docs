# Landscape

Decentralized Physical Infrastructure Networks (DePIN) are emerging as a vital component of the decentralized web, enabling various services, such as file storage, cloud computing, and more, by leveraging blockchain technology. This review focuses on ten major DePIN solutions, specifically evaluating their levels of decentralization in the context of file storage. Flashback firmly believes educating people is the first step to understanding our project and the years of R\&D behind it.

{% tabs %}
{% tab title="ICP" %}
**Decentralization Level:** Level 3-4 (with a mix of decentralization and centralization due to its unique architecture and governance model)

**Review:** The Internet Computer, developed by the DFINITY Foundation, is a blockchain project that aims to extend the public internet to host backend software, transforming it into a global, decentralized computing platform. The Internet Computer is designed to support applications of any scale, with the vision of decentralizing the internet by enabling developers to deploy software directly on the public internet without relying on traditional IT infrastructure such as cloud services.

**Network Structure and Consensus Mechanism:** The Internet Computer utilizes a unique consensus mechanism called Threshold Relay, combined with Chain Key Technology. The network comprises independent data centers running specialized hardware known as nodes, organized into subnets. These subnets collectively validate and execute smart contracts, known as canisters, on the Internet Computer.

The network’s governance is managed by the Network Nervous System (NNS), a decentralized autonomous organization (DAO) that oversees the protocol's upgrades, economic parameters, and node operator decisions. The NNS is controlled by holders of the ICP token, who can vote on proposals that affect the network.

**Impact on Decentralization:** The Internet Computer's design introduces decentralized and centralized elements. On one hand, the network’s ability to run decentralized applications (dApps) without traditional servers is a significant step toward decentralizing the internet. On the other hand, the role of the NNS introduces centralization risks, as it has considerable power over network governance and operations.

**Level 3-4 Evaluation:**

* **Service Providers:** Developers can deploy dApps directly onto the Internet Computer, bypassing traditional IT infrastructure. This aspect of the network is highly decentralized, as it allows for open and permissionless development.
* **Infrastructure Providers:** Node operators, independent data centers, run the infrastructure of the Internet Computer. However, these nodes must meet specific hardware requirements and are subject to approval by the NNS, which introduces a level of centralization in the network's infrastructure layer.
* **Consensus Mechanism:** The Threshold Relay consensus mechanism is designed to be decentralized, but the NNS’s ability to control node configurations and network upgrades can centralize control. While the NNS operates as a DAO, its decisions can significantly impact the network, leading to potential centralization in governance.
* **Economic Model:** The Internet Computer uses ICP tokens for network transactions and governance. While the NNS controls many aspects of the network’s economic model, token holders can vote on proposals, providing a degree of decentralization in decision-making. However, large token holders can exert disproportionate influence over governance decisions, leading to potential centralization.
* **Network Evolution:** The NNS governs the evolution of the Internet Computer, with token holders voting on proposals. Although the system is designed to be decentralized, the centralization risk arises from the NNS’s control over critical network decisions and its ability to approve or reject node operators.

**Conclusion:** The Internet Computer exhibits a mixed level of decentralization, operating primarily at Level 3 with certain aspects that could approach Level 4. While it decentralizes application deployment and aims to transform the internet into a decentralized platform, the governance model through the NNS introduces centralization risks. The NNS’s control over infrastructure, network upgrades, and economic parameters means that while the Internet Computer enables decentralized computing, it also retains elements of centralized control, particularly in network governance and infrastructure management.
{% endtab %}

{% tab title="FIL" %}
**Decentralization Level:** Level 3 (with centralization aspects due to Filecoin Plus)

**Review:** Filecoin is a decentralized storage network that allows users to rent out unused hard drive space. It uses a unique combination of Proof-of-Replication (PoRep) and Proof-of-Spacetime (PoSt) to ensure data is stored securely and retrievably over time. Filecoin’s network is designed to be decentralized, allowing anyone to participate as a storage provider and earn FIL tokens as rewards.

**Filecoin Plus (Filecoin+):** Filecoin Plus is an initiative within the Filecoin ecosystem that aims to improve the quality and reliability of storage services by adding a layer of trust and verification. This program allows clients who want to store valuable data on the network to receive data caps, essentially larger storage deals with verified storage providers. These providers are vetted through a governance process that involves community-driven notaries who verify the legitimacy of the data and the storage provider.

**Impact on Decentralization:** While the core Filecoin protocol remains decentralized, the introduction of Filecoin Plus adds a layer of centralization in the form of notaries and the verification process. This governance structure introduces a degree of central oversight, as notaries have significant influence over which storage providers receive the enhanced data caps and can participate in the more critical deals. The reliance on a vetted group of notaries means that, although the storage and retrieval processes are decentralized, the initial verification and trust layer is only partially permissionless.

**Level 3 Evaluation:**

* **Service Providers:** Filecoin allows for decentralized service provision; however, the influence of notaries in Filecoin Plus means that certain providers have a more privileged status.
* **Infrastructure Providers:** Storage providers can freely contribute to the network, but participation in Filecoin Plus requires additional verification.
* **Consensus Mechanism:** Filecoin’s PoRep and PoSt are cryptographically sound and do not rely on human intervention; however, the economic benefits of Filecoin Plus create an uneven playing field.
* **Economic Model:** Filecoin's reward mechanism is decentralized, but Filecoin Plus introduces a layer of centralized control in the form of notaries.
* **Network Evolution:** The Filecoin protocol is open-source and governed by its community, but the Filecoin Plus program adds a semi-centralized layer that influences which providers can grow more rapidly within the network.

**Conclusion:** Filecoin operates at a Level 3 decentralization when considering the centralizing influence of Filecoin Plus. While the core network remains decentralized, the Filecoin Plus program introduces elements of centralization that impact the overall governance and operation of the network, particularly in terms of economic incentives and service provider participation.
{% endtab %}

{% tab title="AR" %}
**Decentralization Level:** Level 4 (with centralization concerns due to proprietary Proof of Access mechanism)

**Review:** Arweave is a decentralized storage network that introduces a novel consensus mechanism called Proof of Access (PoA). Unlike traditional Proof of Work (PoW) or Proof of Stake (PoS), Arweave’s PoA ensures that miners must prove they can access a random previous block in the blockchain, incentivizing the long-term storage of data. This mechanism aims to create a permanent, tamper-resistant record of data stored on the network, with miners rewarded for maintaining and providing access to this data over time.

**Proof of Access (PoA):** Proof of Access is a proprietary consensus algorithm developed by Arweave. It works by requiring miners to provide cryptographic proof that they can access a randomly selected previous block (which contains data) from the blockchain. This mechanism is designed to ensure that the entire chain, or at least significant portions of it, are constantly being stored by active participants in the network. Unlike PoW, where miners are incentivized solely based on computational power, PoA rewards those who can demonstrate continued storage of data.

**Impact on Decentralization:** While Arweave’s PoA mechanism is innovative in promoting data permanence, its proprietary nature raises concerns regarding decentralization. The proprietary aspect of PoA means that the consensus mechanism is not widely adopted outside of Arweave, potentially limiting the network’s decentralization. Additionally, because PoA is unique to Arweave, there is a dependency on the protocol’s developers for maintenance and updates, introducing a level of centralization in governance and protocol evolution.

**Level 4 Evaluation:**

* **Service Providers:** Arweave allows decentralized service provision, with anyone able to participate as a storage provider. However, the proprietary nature of PoA may limit the accessibility and understanding of the protocol to those outside the Arweave ecosystem.
* **Infrastructure Providers:** While infrastructure providers can freely contribute to the network, the use of PoA may create barriers to entry, as it requires specific knowledge and compliance with Arweave’s unique consensus mechanism.
* **Consensus Mechanism:** PoA is a decentralized consensus mechanism but is not permissionless in the broader sense due to its proprietary design. The consensus is independent of human action but tied to the specificities of Arweave’s protocol.
* **Economic Model:** The economic incentives in Arweave are tied to PoA, which rewards those who store data long-term. However, the reliance on a proprietary system introduces a layer of centralization, as the protocol's economics are tightly controlled by Arweave’s developers.
* **Network Evolution:** Arweave’s protocol is open-source, but the proprietary nature of PoA means that the evolution of the network is somewhat centralized, with changes and updates potentially dependent on the core development team.

**Conclusion:** Arweave operates at a Level 4 decentralization when considering the proprietary aspects of its Proof of Access mechanism. While the network itself is decentralized and allows for broad participation, the reliance on a unique, proprietary consensus mechanism introduces centralization concerns. These concerns are particularly relevant in terms of protocol governance, economic incentives, and network evolution, which are all influenced by the proprietary nature of PoA.
{% endtab %}

{% tab title="AIOZ" %}
**Decentralization Level:** Level 3 (with potential centralization due to network structure and content delivery mechanisms)

**Review:** AIOZ Network is a decentralized content delivery network (CDN) that leverages blockchain technology to create a distributed network of nodes that stream and store media content. The network aims to disrupt traditional CDNs by offering a decentralized alternative that is more scalable, cost-effective, and efficient. AIOZ uses its native blockchain to manage and incentivize the nodes that contribute bandwidth, storage, and computing power to the network.

**Network Structure and Consensus Mechanism:** AIOZ Network employs a hybrid consensus mechanism combining Delegated Proof of Stake (DPoS) and Proof of Storage. In DPoS, token holders vote to elect a limited number of validators who are responsible for block production and network governance. Proof of Storage, on the other hand, incentivizes nodes to provide storage for media content, ensuring the availability and integrity of data on the network.

**Impact on Decentralization:** While AIOZ aims to decentralize content delivery, the use of DPoS introduces elements of centralization. In DPoS, a small number of elected validators are responsible for maintaining the blockchain, which can lead to centralization if a few entities control the majority of voting power. Additionally, while Proof of Storage decentralizes content storage, the reliance on DPoS for network governance may create a centralization risk if the validator set is not sufficiently diverse.

**Level 3 Evaluation:**

* **Service Providers:** AIOZ allows service providers to deploy on the network, offering a decentralized alternative to traditional CDNs. However, the DPoS mechanism means that the network's operations are influenced by the elected validators, potentially centralizing control.
* **Infrastructure Providers:** Anyone can contribute to the network by running a node and providing storage or bandwidth. However, the economic incentives and governance decisions are influenced by the small number of validators elected through DPoS.
* **Consensus Mechanism:** The hybrid consensus mechanism combines decentralized and centralized elements. While Proof of Storage promotes decentralization, the DPoS model introduces centralization risks due to the limited number of validators.
* **Economic Model:** The network incentivizes participants through AIOZ tokens, with rewards distributed based on contributions to content delivery and storage. However, the DPoS governance model centralizes decision-making power in the hands of a few validators.
* **Network Evolution:** AIOZ is open-source, and the community can propose changes to the network. However, the DPoS governance model means that the ultimate decision-making power lies with the elected validators, potentially centralizing control over the network's evolution.

**Conclusion:** AIOZ Network operates at a Level 3 decentralization, with a hybrid consensus mechanism that balances decentralization and centralization. The use of DPoS introduces centralization risks, particularly in governance, where a small number of validators have significant influence over the network. While the Proof of Storage mechanism promotes decentralization by incentivizing a broad base of participants, the overall level of decentralization is moderated by the centralization risks inherent in DPoS.
{% endtab %}

{% tab title="HOLO" %}
**Decentralization Level:** Level 2-3 (Moderate decentralization with significant centralized aspects, particularly in its consensus and storage mechanisms)

**Review:**

Holo is a decentralized hosting platform that bridges the traditional internet and Holochain, an open-source framework for developing fully distributed peer-to-peer applications. Holochain applications (hApps) operate without the need for traditional consensus algorithms, and instead, each participant maintains their own local chain and storage. Holo aims to provide decentralized hosting services for these hApps, enabling them to be accessed by regular web users.

**Network Structure and Consensus Mechanism:**

Unlike traditional blockchain-based networks, Holochain does not rely on global consensus. Instead, it uses a unique approach where each node (participant) maintains its own local hash chain and operates independently. This means that every user of a Holochain application (hApp) has their own ledger, and there is no need for all nodes to agree on a single global state.

Holo, on the other hand, acts as a bridge, allowing hApps to be hosted and accessed by web users. Holo hosts, who provide their computing resources to host hApps, are rewarded in HoloFuel, a currency native to the Holo ecosystem.

**Impact on Decentralization:**

Holo's approach to decentralization is unique but also introduces several centralized elements. While Holochain itself is designed to operate in a fully decentralized manner, Holo's infrastructure, especially its consensus mechanism and hosting services, introduces centralization.

**Level 2-3 Evaluation:**

* **Service Providers:** Holo allows developers to create decentralized applications using Holochain, and these applications can be hosted on Holo's network of hosts. However, the hosting service itself has centralized components, as HoloFuel transactions and the hosting marketplace are managed within the Holo ecosystem. This limits the overall decentralization of the service layer.
* **Infrastructure Providers:** Holo hosts are independent participants who provide storage and processing power. While this appears decentralized, the infrastructure is managed centrally by Holo, including the issuance and management of HoloFuel. The central authority's role in managing these aspects introduces a level of centralization in the infrastructure.
* **Consensus Mechanism:** Holochain does not use a traditional consensus mechanism like Proof-of-Work or Proof-of-Stake. Instead, each node operates independently, which can be seen as a decentralized approach. However, the reliance on HoloFuel and the central management of host payments bring some centralization to the network.
* **Economic Model:** The economic model is based on HoloFuel, which is centrally issued and managed. While hosts can earn HoloFuel by providing services, the central control over the currency and the hosting marketplace introduces a significant degree of centralization.
* **Network Evolution:** The evolution of Holo and Holochain is governed by the Holo organization. While the project is open-source and encourages community contributions, the central authority retains control over the development and direction of the network, limiting the decentralization of network governance.

**Conclusion:**

Holo operates at a decentralization level between Level 2 and 3. While it introduces innovative concepts for decentralized application hosting and local consensus through Holochain, the infrastructure and economic model are centrally managed. The use of a local chain for each participant in Holochain adds a unique layer of decentralization, but the overall system's reliance on centralized control for HoloFuel and host management diminishes the decentralization of the network. As a result, Holo represents a hybrid model where decentralized technology is supported by centralized infrastructure and economic mechanisms.
{% endtab %}

{% tab title="SIA" %}
**Decentralization Level:** Level 3-4 (High decentralization in storage operations with moderate centralization in governance and economic model)

**Review:**

Siacoin is a decentralized cloud storage platform allowing users to rent out unused hard drive space to those needing storage. This peer-to-peer model leverages blockchain technology to create a decentralized marketplace where users can buy and sell storage space, ensuring that no single entity controls the data. Siacoin, the native cryptocurrency, facilitates payments on the network.

**Network Structure and Consensus Mechanism:**

Siacoin uses a Proof-of-Work (PoW) consensus mechanism, similar to Bitcoin, to secure the network. This consensus mechanism ensures that the network remains decentralized by allowing participants to contribute their computational power to validate transactions and secure the blockchain. This decentralized setup prevents any single party from controlling the network.

Data stored on the Sia network is divided into pieces, each encrypted and distributed across multiple hosts. This process ensures data redundancy and security, as no single host can access the stored data. Additionally, Sia uses smart contracts, known as "file contracts," to automate and enforce the terms of storage agreements between renters and hosts.

**Impact on Decentralization:**

Siacoin’s design emphasizes decentralization, particularly in how storage is managed. The network's reliance on a distributed set of hosts to store data and use cryptographic techniques to secure and manage this data reinforces this decentralization. However, certain ecosystem elements introduce some centralization, particularly around governance and economic aspects.

**Level 3-4 Evaluation:**

* **Service Providers:** In Siacoin’s ecosystem, service providers (hosts) can freely offer their storage space on the network. The decentralized nature of the storage process means that no central authority can censor or control the use of storage on the network. This aligns with a high level of decentralization, as it allows for a permissionless market where anyone can participate.
* **Infrastructure Providers:** Infrastructure providers in Siacoin’s network are individual hosts who provide storage space. These hosts operate independently, and smart contracts govern their interactions with the network. The decentralized management of storage operations means that infrastructure providers have complete control over their participation, with minimal central oversight.
* **Consensus Mechanism:** Siacoin’s Proof-of-Work consensus mechanism supports the network's decentralization by allowing participants to validate transactions. This decentralized approach to consensus is a critical aspect of Siacoin's design, ensuring that no single entity can dominate the network.
* **Economic Model:** Siacoin's economic model is relatively decentralized. Payments for storage services are made in Siacoin, and smart contracts govern these transactions without intermediaries. However, the development and direction of the network are overseen by a centralized team (Nebulous, the company behind Sia), which introduces some level of centralization in decision-making processes and long-term governance.
* **Network Evolution:** The evolution of Siacoin is somewhat centralized. While the network operates decentralized, the Nebulous team manages the development and implementation of new features and updates. This means that while the operational aspects of the network are decentralized, the governance and development could be more decentralized.

**Conclusion:**

Siacoin operates at a decentralization level between Levels 3 and 4. The network excels in decentralizing storage operations, allowing a broad and distributed set of participants to provide and access storage. However, certain aspects of the network, particularly related to governance and economic control, remain centralized. The use of Proof-of-Work contributes to the network's security and decentralization, but the central role of Nebulous in development and decision-making tempers this somewhat. Overall, Siacoin represents a robust decentralized storage solution with some centralized elements in its broader ecosystem management.
{% endtab %}

{% tab title="BLZ" %}
**Decentralization Level:** Level 2-3 (Moderate decentralization in storage operations with centralized elements in network management and consensus)

**Review:**

Bluzelle is a decentralized storage network that primarily focuses on providing scalable data storage solutions for decentralized applications (dApps). Bluzelle aims to offer a decentralized database and data storage solution, often leveraging technologies like IPFS (InterPlanetary File System) for distributed data storage. However, unlike fully decentralized networks, Bluzelle integrates some centralized elements in its architecture, particularly in network management and consensus mechanisms.

**Network Structure and Consensus Mechanism:**

Bluzelle employs a Byzantine Fault Tolerance (BFT) consensus mechanism within its network. This type of consensus is known for its ability to operate in environments where some nodes might act maliciously, making it a suitable choice for networks that require high fault tolerance. However, the BFT mechanism in Bluzelle is less decentralized than traditional Proof-of-Work (PoW) or Proof-of-Stake (PoS) consensus mechanisms, as it typically involves a smaller number of participating nodes (validators) that must agree on the state of the

Bluzelle's storage model leverages IPFS for the distribution of files across a network of nodes. While IPFS itself is decentralized, Bluzelle's integration of IPFS appears to be more controlled, with a focus on ensuring data availability and integrity within a specific set of nodes. This suggests a hybrid model where decentralization is applied to storage, but with significant oversight from Bluzelle's infrastructure.

**Impact on Decentralization:**

Bluzelle's approach to decentralization is mixed. On one hand, it employs decentralized technologies like IPFS for storage, but on the other hand, it incorporates centralized elements in the form of BFT consensus and network management, where a limited number of validators control the consensus process.

**Level 2-3 Evaluation:**

* **Service Providers:** In Bluzelle’s ecosystem, service providers can deploy their applications on top of the network, but the level of control they have over their deployment might be limited by the central management of the network. This places Bluzelle at a Level 2 for service providers, as the network's parameters and business models are not entirely free from centralized control.
* **Infrastructure Providers:** Infrastructure providers in Bluzelle, particularly those participating as nodes in the IPFS network, have a certain degree of autonomy. However, because Bluzelle manages the consensus mechanism and potentially oversees the storage network, these providers do not have the same level of freedom as in more decentralized networks. This aligns Bluzelle with a Level 2-3 for infrastructure providers.
* **Consensus Mechanism:** The BFT consensus mechanism used by Bluzelle involves a smaller set of validators, which centralizes decision-making to some extent. This approach contrasts with more decentralized networks that allow broader participation in consensus. Therefore, Bluzelle’s consensus mechanism is more centralized, corresponding to a Level 2.
* **Economic Model:** Bluzelle’s economic model is likely influenced by its centralized management of the network. While it may offer incentives for participation, the overall structure is more controlled compared to completely decentralized networks. This aligns with Level 2, where the network economy is not entirely permissionless and is managed to a significant degree by a central entity.
* **Network Evolution:** The evolution of Bluzelle is managed by a centralized team, similar to other projects with strong central oversight. This means that the introduction of new features, updates, and governance decisions are likely controlled by Bluzelle’s core team, rather than being driven by a decentralized community. This places Bluzelle at Level 2 in terms of network evolution.

**Conclusion:**

Bluzelle operates at a decentralization level between Level 2 and 3. The network leverages decentralized storage technologies like IPFS but integrates them into a framework that is overseen by a more centralized management structure. The use of BFT for consensus further centralizes the network, as it restricts the number of participants in the consensus process. Overall, while Bluzelle adopts some decentralized principles, its approach to network management and consensus introduces a level of centralization that limits its positioning on the decentralization spectrum.
{% endtab %}

{% tab title="STORJ" %}

{% endtab %}
{% endtabs %}
