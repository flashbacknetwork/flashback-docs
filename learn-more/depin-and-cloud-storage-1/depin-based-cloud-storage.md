# DePIN-based Cloud Storage

## The Origin of DePIN in Cloud Storage

The emergence of Decentralized Physical Infrastructure Networks (DePIN) in cloud storage can be traced back to the growing demand for a more secure, cost-effective, and decentralized alternative to traditional cloud storage solutions. Centralized cloud storage providers, while offering significant convenience and scalability, have raised concerns over issues like data privacy, control, and single points of failure. These concerns have driven the development of decentralized storage networks, which aim to address the vulnerabilities inherent in centralized systems.

Pioneering projects like Filecoin and Arweave were among the first to explore the potential of decentralized storage by leveraging blockchain technology. These projects laid the foundational principles of DePIN by creating networks where users could rent out their unused storage capacity on personal devices, thus contributing to a decentralized and distributed storage ecosystem. The core idea was to remove reliance on centralized servers and instead distribute data across a network of independent nodes operated by individual participants. This approach promised enhanced security, as data would be stored in a distributed manner, making it harder for any single point of failure to compromise the entire system.

## The Current Landscape

DePIN-based cloud storage is emerging as a vital component of the decentralized web. By leveraging blockchain technology, they enable various services, such as file storage, cloud computing, and more. This review, in line with Flashback's belief in the power of education, focuses on listed DePIN-based cloud storage solutions (FDV of +$10m market cap), specifically evaluating their levels of decentralization in the context of data storage. We listed only projects that natively integrated data storage. For instance, OORT proposes data storage projects using other infrastructure.

Below, we included a list of projects that summarize the various attractions of the technologies. The level of decentralization achieved is defined by the project's inability to validate the next level.

### +$100m marketcap projects

{% tabs %}
{% tab title="ICP" %}
**Decentralization:** Level 1 (Very low decentralization; centralized concerns with NNS)

**Review:** The Internet Computer, developed by the DFINITY Foundation, is a blockchain project that aims to extend the public internet to host backend software, transforming it into a global, decentralized computing platform. The Internet Computer is designed to support applications of any scale. Its vision is to decentralize the internet by enabling developers to deploy software directly on the public internet without relying on traditional IT infrastructure such as cloud services.

**Network Structure and Consensus Mechanism:** The Internet Computer utilizes a unique consensus mechanism called Threshold Relay, combined with Chain Key Technology. The network comprises independent data centers running specialized hardware and nodes organized into subnets. These subnets collectively validate and execute smart contracts, known as canisters, on the Internet Computer.

The network’s governance is managed by the Network Nervous System (NNS), a decentralized autonomous organization (DAO) that oversees the protocol's upgrades, economic parameters, and node operator decisions. The NNS is controlled by holders of the ICP token, who can vote on proposals that affect the network.

**Impact on Decentralization:** The Internet Computer's design introduces decentralized and centralized elements. On one hand, the network’s ability to run decentralized applications (dApps) without traditional servers is a significant step toward decentralizing the Internet. On the other hand, the role of the NNS introduces centralization risks, as it has considerable power over network governance and operations.

**Level Evaluation:**

* **Service Providers:** Developers can deploy dApps directly onto the Internet Computer, bypassing traditional IT infrastructure. This aspect of the network is highly decentralized, as it allows for open and permissionless development.
* **Infrastructure Providers:** Node operators and independent data centers run the Internet Computer's infrastructure. However, these nodes must meet specific hardware requirements and are subject to approval by the NNS, which introduces a level of centralization in the network's infrastructure layer.
* **Consensus Mechanism:** The Threshold Relay consensus mechanism is designed to be decentralized, but the NNS’s ability to control node configurations and network upgrades can centralize control. While the NNS operates as a DAO, its decisions can significantly impact the network, leading to potential centralization in governance.
* **Economic Model:** The Internet Computer uses ICP tokens for network transactions and governance. While the NNS controls many aspects of the network’s economic model, token holders can vote on proposals, providing a degree of decentralization in decision-making. However, large token holders can exert disproportionate influence over governance decisions, leading to potential centralization.
* **Network Evolution:** The NNS governs the evolution of the Internet Computer, with token holders voting on proposals. Although the system is designed to be decentralized, the centralization risk arises from the NNS’s control over critical network decisions and its ability to approve or reject node operators.
{% endtab %}

{% tab title="BTT" %}
**Decentralization**: Level 2 (Low decentralization with a lack of storage consensus)

**Review:**

BitTorrent, originally a peer-to-peer (P2P) file-sharing protocol, has evolved into a decentralized platform with the integration of blockchain technology, primarily through its token, BitTorrent Token (BTT). BitTorrent aims to enhance the efficiency and scalability of file sharing by leveraging decentralized storage and blockchain-based incentives. However, the platform still retains certain centralized components, particularly in its governance and economic structures.

**Network Structure and Consensus Mechanism:** BitTorrent operates on a decentralized P2P network, where users (peers) share files directly with each other. The integration of blockchain technology introduces BTT, which incentivizes users to share files and resources more efficiently. BitTorrent’s core technology is its P2P network, which allows users to distribute files without relying on a central server. Each user in the network can act as both a client and a server, sharing and receiving parts of files from multiple sources simultaneously. This method increases download speeds and ensures redundancy.

BitTorrent, through its integration with the TRON blockchain, relies on a delegated Proof-of-Stake (DPoS) consensus mechanism, where Super Representatives validate transactions and maintain the network. This mechanism introduces centralization, as only a limited number of SRs are involved in the consensus process.

**Impact on Decentralization:** While BitTorrent's file-sharing protocol is inherently decentralized, introducing BTT and using TRON’s DPoS consensus mechanism add centralized elements to the platform.

**Level Evaluation:**

* **Service Providers**: BitTorrent service providers include users who share files and contribute resources to the network. The P2P nature of BitTorrent allows for a high degree of decentralization in how files are shared and accessed. However, the platform's governance, particularly through the TRON blockchain, is more centralized.
* **Infrastructure Providers**: The infrastructure of BitTorrent is primarily decentralized, as it relies on a vast network of users who share files. However, the introduction of BTT and its reliance on the TRON blockchain introduce centralized control, particularly in how economic incentives are managed and distributed.
* **Consensus Mechanism**: The DPoS meTRON's DPoS mechanismBitTorrent's infrastructure used by TRON involves a limited number of Super Representatives, which centralizes the validation process to some extent. This contrasts with more decentralized consensus mechanisms like PoW or PoS, where a larger number of nodes participate in consensus.
* **Economic Model**: BitTorrent’s economic model is influenced by its integration with the TRON blockchain. While users can earn BTT for contributing resources, the distribution and management of these tokens are governed by centralized protocols. This centralized control over the economic incentives can limit the overall decentralization of the platform.
* **Network Evolution**: The evolution of BitTorrent is largely guided by its parent company, TRON. Updates and changes to the platform are likely controlled by the TRON team, with limited input from the broader community. This centralization in governance further limits the decentralization of the netw
{% endtab %}

{% tab title="FIL" %}
**Decentralization:** Level 1 (Very low Decentralization if using centralized notaries with Filecoin Plus) and Level 4 (High Decentralization without Filecoin Plus)

**Review:** Filecoin is a decentralized storage network that allows users to rent out unused hard drive space. It uses a unique combination of Proof-of-Replication (PoRep) and Proof-of-Spacetime (PoSt) to ensure data is stored securely and retrievably over time. Filecoin’s network is designed to be decentralized, allowing anyone to participate as a storage provider and earn FIL tokens as rewards.

**Filecoin Plus (Filecoin+):** Filecoin Plus is an initiative within the Filecoin ecosystem that aims to improve the quality and reliability of storage services by adding a layer of trust and verification. This program allows clients who want to store valuable data on the network to receive data caps, essentially larger storage deals with verified storage providers. These providers are vetted through a governance process that involves community-driven notaries who verify the legitimacy of the data and the storage provider.

**Impact on Decentralization:** While the core Filecoin protocol remains decentralized, the introduction of Filecoin Plus adds a layer of centralization in the form of notaries and the verification process. This governance structure introduces a degree of central oversight, as notaries have significant influence over which storage providers receive the enhanced data caps and can participate in the more critical deals. The reliance on a vetted group of notaries means that, although the storage and retrieval processes are decentralized, the initial verification and trust layer is only partially permissionless.

**Level Evaluation:**

* **Service Providers:** Filecoin allows for decentralized service provision; however, the influence of notaries in Filecoin Plus means that certain providers have a more privileged status.
* **Infrastructure Providers:** Storage providers can freely contribute to the network. Filecoin Plus requires additional centralized verifications.
* **Consensus Mechanism:** Filecoin’s PoRep and PoSt are cryptographically sound and do not rely on human intervention; however, the economic benefits of Filecoin Plus create an uneven playing field.
* **Economic Model:** Filecoin's reward mechanism is decentralized, but Filecoin Plus introduces a layer of centralized control in the form of notaries.
* **Network Evolution:** The Filecoin protocol is open-source and governed by its community. However, the Filecoin Plus program led by Protocol Labs adds a semi-centralized layer that influences which providers can grow more rapidly within the network. The dominance of Filecoin foundation and Protocol Labs do not fit with the decentralization aspects of the network evolution.
{% endtab %}

{% tab title="AR" %}
**Decentralization:** Level 2 (Low decentralization due to the proprietary nature of the consensus)

**Review:** Arweave is a decentralized storage network introducing a novel consensus mechanism called Proof of Access (PoA). Unlike traditional Proof of Work (PoW) or Proof of Stake (PoS), Arweave’s PoA ensures that miners must prove they can access a random previous block in the blockchain, incentivizing the long-term storage of data. This mechanism aims to create a permanent, tamper-resistant record of data stored on the network, with miners rewarded for maintaining and providing access to this data over time.

**Proof of Access (PoA):** Proof of Access is a proprietary consensus algorithm developed by Arweave. It works by requiring miners to provide cryptographic proof that they can access a randomly selected previous block (which contains data) from the blockchain. This mechanism is designed to ensure that the entire chain, or at least significant portions, are constantly being stored by active participants in the network. Unlike PoW, where miners are incentivized solely based on computational power, PoA rewards those who can demonstrate continued data storage.

**Impact on Decentralization:** While Arweave’s PoA mechanism is innovative in promoting data permanence, its proprietary nature raises concerns regarding decentralization. The proprietary aspect of PoA means that the consensus mechanism is not widely adopted outside of Arweave, potentially limiting the network’s decentralization. Additionally, because PoA is unique to Arweave, there is a dependency on the protocol’s developers for maintenance and updates, introducing a level of centralization in governance and protocol evolution.

**Level Evaluation:**

* **Service Providers:** Arweave allows decentralized service provision, with anyone able to participate as a service provider. No indicator may limit the protocol's accessibility and understanding to those outside the Arweave ecosystem.
* **Infrastructure Providers:** While infrastructure providers can freely contribute to the network, using PoA may create barriers to entry, as it requires specific knowledge and compliance with Arweave’s unique consensus mechanism.
* **Consensus Mechanism:** PoA is a decentralized consensus mechanism, but due to its proprietary design, it is not permissionless in the broader sense. The consensus is independent of human action but tied to the specificities of Arweave’s protocol.
* **Economic Model:** Arweave's economic incentives are tied to PoA, which rewards those who store data long-term. However, relying on a proprietary system introduces a layer of centralization, as Arweave’s developers tightly control the protocol's economics.
* **Network Evolution:** Arweave’s protocol is open-source, but PoA's proprietary nature means that the network's evolution is somewhat centralized, with changes and updates potentially dependent on the core development team.
{% endtab %}

{% tab title="AIOZ" %}
**Decentralization:** Level 2 (Low decentralization due to the DPoS and very high limitations of validators)

**Review:** AIOZ Network is a decentralized content delivery network (CDN) that leverages blockchain technology to create a distributed network of nodes that stream and store media content. The network aims to disrupt traditional CDNs by offering a decentralized alternative that is more scalable, cost-effective, and efficient. AIOZ uses its native blockchain to manage and incentivize the nodes that contribute bandwidth, storage, and computing power to the network.

**Network Structure and Consensus Mechanism:** AIOZ Network employs a hybrid consensus mechanism combining Delegated Proof of Stake (DPoS) and Proof of Storage. In DPoS, token holders vote to elect a limited number of validators responsible for block production and network governance. On the other hand, Proof of Storage incentivizes nodes to provide storage for media content, ensuring the availability and integrity of data on the network.

**Impact on Decentralization:** While AIOZ aims to decentralize content delivery, the use of DPoS introduces elements of centralization. In DPoS, a few elected validators are responsible for maintaining the blockchain, which can lead to centralization if a few entities control the majority of voting power. Additionally, while Proof of Storage decentralizes content storage, relying on DPoS for network governance may create a centralization risk if the validator set is sufficiently diverse.

**Level Evaluation:**

* **Service Providers:** AIOZ allows service providers to deploy on the network, offering a decentralized alternative to traditional CDNs. However, the DPoS mechanism means that the elected validators influence the network's operations, potentially centralizing control of service providers. Nonetheless, the service provider can participate without permission at first glance.
* **Infrastructure Providers:** Anyone can contribute to the network by running a node and providing storage or bandwidth. However, the economic incentive and small number of validators elected through DPoS influence the economic incentives and governance decisions, which are influenced by the small number of validators elected through DPoS.
* **Consensus Mechanism:** The hybrid consensus mechanism combines decentralized and centralized elements. While Proof of Storage promotes decentralization, the DPoS model introduces a high degree of centralization and governance risks for the storage duties due to the limited number of validators.
* **Economic Model:** The network incentivizes participants through AIOZ tokens, with rewards distributed based on content delivery and storage contributions. However, the DPoS governance model centralizes decision-making power in the hands of a few validators.
* **Network Evolution:** AIOZ is open-source, and the community can propose changes to the network. However, the DPoS governance model means that the ultimate decision-making power lies with the elected validators, potentially centralizing control over the network's evolution.
{% endtab %}

{% tab title="HOLO" %}
**Decentralization:** Level 1 (Very low decentralization because of concerns with HoloFuel)

**Review:** Holo is a decentralized hosting platform that bridges the traditional internet and Holochain, an open-source framework for developing fully distributed peer-to-peer applications. Holochain applications (hApps) operate without traditional consensus algorithms; instead, each participant maintains their own local chain and storage. Holo aims to provide decentralized hosting services for these hApps, enabling them to be accessed by regular web users.

**Network Structure and Consensus Mechanism:** Holochain does not rely on global consensus, unlike traditional blockchain-based networks. Instead, it uses a unique approach where each node (participant) maintains its local hash chain and operates independently. This means that every user of a Holochain application (hApp) has their ledger, and there is no need for all nodes to agree on a single global state.

Holo, on the other hand, acts as a bridge, allowing web users to host and access hApps. Holo hosts, who provide their computing resources to host hApps, are rewarded in HoloFuel, a currency native to the Holo ecosystem.

**Impact on Decentralization:** Holo's approach to decentralization is unique but also introduces several centralized elements. While Holochain itself is designed to operate fully decentralized, Holo's infrastructure, especially its consensus mechanism and hosting services, introduces centralization.

**Level Evaluation:**

* **Service Providers:** Holo allows developers to create decentralized applications using Holochain, which can be hosted on Holo's network of hosts. There are no specific centralization aspects limiting the use of Holo protocols by services.
* **Infrastructure Providers:** Holo hosts are independent participants who provide storage and processing power. While this appears decentralized, Holo manages the infrastructure centrally, including the issuance and management of HoloFuel. The central authority's role in managing these aspects introduces a level of centralization in the infrastructure.
* **Consensus Mechanism:** Holochain does not use a traditional consensus mechanism like Proof-of-Work or Proof-of-Stake. Instead, each node operates independently, which can be seen as a decentralized approach. However, the reliance on HoloFuel and the central management of host payments bring some centralization to the network.
* **Economic Model:** The economic model is based on HoloFuel, which is centrally issued and managed. While hosts can earn HoloFuel by providing services, the central control over the currency and the hosting marketplace introduces a significant degree of centralization.
* **Network Evolution:** The evolution of Holo and Holochain is governed by the Holo organization. While the project is open-source and encourages community contributions, the central authority retains control over the development and direction of the network, limiting the decentralization of network governance.
{% endtab %}

{% tab title="SIA" %}
**Decentralization:** Level 4 (High decentralization while improving the decentralization of network evolution)

**Review:** Siacoin is a decentralized cloud storage platform allowing users to rent unused hard drive space to those needing storage. This peer-to-peer model leverages blockchain technology to create a decentralized marketplace where users can buy and sell storage space, ensuring that no single entity controls the data. Siacoin, the native cryptocurrency, facilitates payments on the network.

**Network Structure and Consensus Mechanism:** Siacoin uses a Proof-of-Work (PoW) consensus mechanism, similar to Bitcoin, to secure the network. This consensus mechanism ensures that the network remains decentralized by allowing participants to contribute their computational power to validate transactions and secure the blockchain. This decentralized setup prevents any single party from controlling the network.

Data stored on the Sia network is divided into pieces, each encrypted and distributed across multiple hosts. This process ensures data redundancy and security, as no single host can access the stored data. Additionally, Sia uses smart contracts, known as "file contracts," to automate and enforce the terms of storage agreements between renters and hosts.

**Impact on Decentralization:** Siacoin’s design emphasizes decentralization, particularly in managing storage. The network's reliance on a distributed set of hosts to store data and use cryptographic techniques to secure and manage this data reinforces this decentralization. However, certain ecosystem elements introduce some centralization, particularly around governance and economic aspects.

**Level Evaluation:**

* **Service Providers:** In Siacoin’s ecosystem, service providers (hosts) can freely offer their storage space on the network. The decentralized nature of the storage process means that no central authority can censor or control the use of storage on the network. This aligns with a high level of decentralization, as it allows for a permissionless market where anyone can participate.
* **Infrastructure Providers:** Infrastructure providers in Siacoin’s network are individual hosts who provide storage space. These hosts operate independently, and smart contracts govern their interactions with the network. The decentralized management of storage operations means that infrastructure providers have complete control over their participation, with minimal central oversight.
* **Consensus Mechanism:** Siacoin’s Proof-of-Work consensus mechanism supports the network's decentralization by allowing participants to validate transactions. This decentralized approach to consensus is a critical aspect of Siacoin's design, ensuring that no single entity can dominate the network.
* **Economic Model:** Siacoin's economic model is relatively decentralized. Payments for storage services are made in Siacoin, and smart contracts govern these transactions without intermediaries.
* **Network Evolution:** The evolution of Siacoin is somewhat centralized. While the network operates decentralized, the Nebulous team develops and implements new features and updates. This means that while the operational aspects of the network are decentralized, the governance and development could be more decentralized.
{% endtab %}

{% tab title="STORJ" %}
**Decentralization:** Level 1 (Very low decentralization because of vetting processes for infrastructure providers)

**Review:** STORJ is a decentralized cloud storage platform enabling users to store data across a globally distributed network. It leverages blockchain technology to offer a more secure, private, and efficient alternative to traditional cloud storage providers. However, despite its decentralized approach to storage, certain aspects of STORJ's network management and economic model introduce centralization elements.

**Network Structure and Consensus Mechanism:** STORJ operates on a decentralized storage network where data is split into smaller pieces, encrypted, and distributed across multiple nodes. The platform ensures data integrity and availability through a series of audits and file verification processes designed to check that nodes are storing data correctly and can retrieve it when requested.

STORJ's verification mechanism for node operators is one key element that introduces centralization. Not all nodes can join the network freely; instead, they undergo a vetting process that includes audits and reputation scoring. This vetting process is crucial for maintaining the integrity of the network but also centralizes control to some extent, as the criteria and processes for verification are determined and overseen by STORJ Labs.

The consensus mechanism in STORJ does not involve traditional blockchain consensus protocols like Proof of Work (PoW) or Proof of Stake (PoS). Instead, it relies on a reputation system and regular audits to ensure that nodes behave correctly. While this approach is efficient, it centralizes the decision-making power regarding which nodes are trusted, as STORJ Labs plays a significant role in managing this system.

**Impact on Decentralization:** STORJ's approach to decentralization is mixed. On the one hand, data distribution across a global network of nodes introduces a significant degree of decentralization in terms of storage. On the other hand, the network's reliance on a centrally managed verification process for nodes and the control over economic aspects like payments and rewards introduce elements of centralization.

**Level Evaluation:**

* **Service Providers:** In STORJ’s ecosystem, service providers can deploy their applications and use the storage network. However, they must interact with a centrally managed economic system that governs payments and rewards.
* **Infrastructure Providers:** Node operators, or infrastructure providers, must undergo a verification process before they can participate in the network. While they do contribute to the network’s decentralized storage system, their participation is controlled by a central authority that manages node verification and reputation.
* **Consensus Mechanism:** STORJ does not use a traditional blockchain consensus mechanism. Instead, it relies on a reputation system and audits, both overseen by a central entity. This limits the decentralization of the consensus process, as decision-making power is concentrated within STORJ Labs.
* **Economic Model:** STORJ's economic model is centralized, with STORJ Labs managing payments, rewards, and pricing structures. This central control contrasts with more decentralized networks, where economic decisions are made by the community or through algorithmic processes.
* **Network Evolution:** STORJ Labs has significant control over the network's development and evolution. While the platform may engage with the community, the ultimate decision-making power rests with the core team, limiting the network’s ability to evolve through decentralized governance processes.

**Conclusion:**

STORJ operates at a decentralization level between Level 2 and 3. While the network leverages decentralized storage technologies to distribute data across a global network of nodes, it incorporates centralized elements in its node verification, economic control, and network management. The verification process for node operators, managed by STORJ Labs, and the central management of payments and rewards, introduce levels of centralization that limit its positioning on the decentralization spectrum. Overall, while STORJ adopts some decentralized principles, its approach to network management and economic control introduces a level of centralization that places it in the middle range of the decentralization scale.
{% endtab %}
{% endtabs %}

### -$100m marketcap projects

{% tabs %}
{% tab title="BLZ" %}
**Decentralization:** Level 2 (Low decentralization in storage operations without decentralized storage consensus)

**Review:** Bluzelle is a decentralized storage network primarily providing scalable data storage solutions for decentralized applications (dApps). It aims to offer a decentralized database and data storage solution, often leveraging technologies like IPFS (InterPlanetary File System) for distributed data storage. However, Bluzelle integrates some centralized elements in its architecture unlike fully decentralized networks, particularly in network management and consensus mechanisms.

**Network Structure and Consensus Mechanism:** Bluzelle employs a Byzantine Fault Tolerance (BFT) consensus mechanism within its network. This type of consensus is known for its ability to operate in environments where some nodes might act maliciously, making it a suitable choice for networks that require high fault tolerance. However, the BFT mechanism in Bluzelle is less decentralized than traditional Proof-of-Work (PoW) or Proof-of-Stake (PoS) consensus mechanisms, as it typically involves a smaller number of participating nodes (validators) that must agree on the state of the

Bluzelle's storage model leverages IPFS to distribute files across a network of nodes. While IPFS itself is decentralized, Bluzelle's integration of IPFS appears to be more controlled, with a focus on ensuring data availability and integrity within a specific set of nodes. This suggests a hybrid model where decentralization is applied to storage but with significant oversight from Bluzelle's infrastructure.

**Impact on Decentralization:** Bluzelle's approach to decentralization is mixed. On the one hand, it employs decentralized technologies like IPFS for storage. Still, on the other hand, it incorporates centralized elements in the form of BFT consensus and network management, where a limited number of validators control the consensus process.

**Level Evaluation:**

* **Service Providers:** In Bluzelle’s ecosystem, service providers can deploy their applications on top of the network, but the network's central management might limit their level of control over their deployment.
* **Infrastructure Providers:** Infrastructure providers in Bluzelle, particularly those participating as nodes in the IPFS network, have a certain degree of autonomy. However, because Bluzelle manages the consensus mechanism and potentially oversees the storage network, these providers do not have the same freedom as in more decentralized networks.
* **Consensus Mechanism:** Bluzelle does not have a native consensus for storage. Bluzelle's BFT consensus mechanism involves a smaller set of validators, which centralizes decision-making to some extent. This approach contrasts with more decentralized networks that allow broader participation in consensus.
* **Economic Model:** Its centralized network management likely influences Bluzelle’s economic model. While it may offer incentives for participation, the overall structure is more controlled than completely decentralized networks.
* **Network Evolution:** Bluzelle's evolution is managed by a centralized team, similar to other projects with strong central oversight. This means that the introduction of new features, updates, and governance decisions are likely controlled by Bluzelle’s core team rather than driven by a decentralized community.
{% endtab %}

{% tab title="SRX" %}
**Decentralization:** Level 2 (Low decentralization because of storage operations without storage consensus)

**Review:** StorX is a decentralized cloud storage platform built on the XDC blockchain network. It aims to provide a secure, private, and efficient storage solution by distributing data across a network of storage nodes. While StorX leverages decentralized principles, several aspects of its network management and governance introduce centralization elements, affecting its overall level of decentralization.

**Network Structure and Consensus Mechanism:** StorX distributes data across a network of storage nodes owned and operated by various network participants. The platform ensures data availability, security, and integrity through encryption and redundancy, where files are split into smaller fragments, encrypted, and distributed across multiple nodes.

However, like other decentralized storage networks, StorX employs a verification mechanism for node operators. To become a node operator, participants must stake SRX tokens (StorX’s native cryptocurrency) and meet certain requirements set by the StorX network.

StorX also uses a consensus mechanism tied to the XDC blockchain, which employs a Delegated Proof of Stake (DPoS) consensus model. In this model, a limited number of validators are elected to participate in the consensus process, which introduces centralization, as only a subset of nodes are involved in securing the network and validating transactions.

**Impact on Decentralization:**

StorX’s decentralization is moderate. Its data distribution model has strong decentralized aspects but significant centralization in network governance and node participation. The reliance on staking and node verification processes managed by the StorX team limits the degree of decentralization, as it creates barriers to entry and central control over who can become a storage provider.

**Level Evaluation:**

* **Service Providers:** Service providers on StorX can deploy their applications and utilize the network’s storage resources.
* **Infrastructure Providers:** Node operators in StorX must stake SRX tokens and meet specific criteria set by the network, which slightly centralizes control over who can contribute to the storage infrastructure.
* **Consensus Mechanism:** StorX does not have a native blockchain consensus mechanism. Instead, it relies on the XDC Network to handle blockchain-based operations such as transactions, staking, and consensus. StorX relies on the DPoS consensus mechanism used by the XinFin blockchain, which centralizes decision-making to a limited number of elected validators. This reduces the level of decentralization in the consensus process compared to networks that allow broader participation.
* **Economic Model:** StorX's economic model is also centralized to some extent, with the StorX team managing the tokenomics and rewards distribution. While storage providers can earn SRX tokens, the network’s core team designs and controls the overall economic framework.
* **Network Evolution:** The evolution of StorX is guided by the StorX team, with limited input from the broader community. This central control over network upgrades, feature development, and governance decisions limits the degree of decentralization, as changes are only partially driven by a decentralized community process.

**Conclusion:**

StorX operates at a decentralization level between Level 2 and 3. While the network uses decentralized storage principles to distribute and manage data, its approach to node verification, governance, and consensus introduces significant centralization. The requirement for staking SRX tokens and the use of a DPoS consensus model centralize aspects of network participation and decision-making, positioning StorX in the middle range of the decentralization spectrum. Overall, while StorX adopts some decentralized principles, its network structure and governance introduce centralized elements that affect its overall level of decentralization.**Decentralization Level**: **Level 3** (Moderate decentralization with strong cryptographic proofs but some centralization in governance and node management)
{% endtab %}

{% tab title="JKL" %}
**Decentralization:** Level 3 (Moderate decentralization with strong cryptographic proofs but some centralization in its economy)

**Review:**

Jackal Protocol is a decentralized storage network that provides secure, private, and scalable storage solutions. It operates on the principles of decentralization by distributing data across a network of nodes, ensuring that no single entity has control over the stored data. However, while Jackal Protocol embraces decentralized storage, there are elements within its governance and node management that introduce centralization, impacting its overall level of decentralization.

**Network Structure and Consensus Mechanism:** Jackal Protocol uses a combination of decentralized storage technologies and blockchain-based consensus mechanisms to ensure data integrity and security. The Jackal Protocol stores data across multiple nodes in a decentralized manner, similar to other decentralized storage solutions like IPFS. Data is encrypted and split into smaller fragments, which are then distributed across the network. This ensures that no single node holds complete data, enhancing privacy and security.

Jackal Protocol employs cryptographic proofs to ensure that storage providers are holding the data they claim to store. These proofs are akin to Proof-of-Storage (PoS) mechanisms used in other decentralized storage networks, providing a robust method for verifying the integrity and availability of data.

**Impact on Decentralization:**

Jackal Protocol strikes a balance between decentralization in storage operations and centralization in governance and node management.

* **Service Providers**: Service providers on Jackal Protocol can deploy applications and services on top of the network, utilizing its decentralized storage capabilities.
* **Infrastructure Providers**: Infrastructure providers, or storage nodes, play a crucial role in the network by storing and managing data. While the storage process is decentralized, the criteria for participating as a node and managing nodes introduce some centralization.
* **Consensus Mechanism**: The cryptographic proofs used in Jackal Protocol ensure a high level of data integrity and security.
* **Economic Model**: Jackal Protocol’s economic model likely involves token incentives for storage providers, similar to other decentralized storage networks. However, the distribution and management of these incentives may be centrally controlled, influencing the network’s overall decentralization.
* **Network Evolution**: The core team behind Jackal Protocol oversees its development and updates. While this ensures stability and coordinated progress, it also introduces a level of centralization in how the network evolves, unlike a fully decentralized governance model where changes are made through on-chain proposals.
{% endtab %}

{% tab title="STOS" %}
**Decentralization:** Level 1 (Very low decentralization because of validation processes of operators)

**Review:** Stratos is a decentralized data mesh that aims to provide a scalable, self-evolving network for decentralized storage, database, and computing. It integrates a blockchain-based incentive mechanism to create a decentralized infrastructure for Web3. Stratos is unique in its attempt to unify decentralized storage, computation, and a decentralized database, which makes it a multi-faceted project with varying levels of decentralization across its different components.

**Network Structure and Consensus Mechanism:** Stratos operates through a decentralized network of storage nodes incentivized to provide storage capacity in exchange for Stratos tokens (STOS). These storage nodes distribute and replicate data across the network, ensuring data redundancy and availability. The data storage is highly decentralized, leveraging a distributed file storage system akin to IPFS, where files are split, encrypted, and spread across various nodes.

The consensus mechanism in Stratos is a blend of Proof-of-Traffic (PoT) and Proof-of-Authority (PoA). PoT is unique to Stratos and measures the traffic nodes generate to ensure they actively provide services to the network. However, PoA introduces centralization, as it involves a limited set of trusted nodes that verify the actions of other nodes. This creates a semi-centralized layer within the network, as only specific nodes can validate transactions.

**Impact on Decentralization:** Stratos exhibits a mix of decentralization levels. Its storage network is highly decentralized, with data spread across numerous nodes, similar to other decentralized storage solutions. However, introducing PoA for transaction verification adds a centralized element to the network's governance and consensus mechanisms. Additionally, the Stratos team governs the economic model, which influences the network's tokenomics and reward distribution.

**Level Evaluation:**

* **Service Providers:** Stratos allows providers to deploy decentralized applications (dApps) and other services on its platform. These providers can utilize the network's decentralized storage and computation resources.
* **Infrastructure Providers:** The PoA layer and the need to meet certain criteria to participate in the network add a level of centralization, as only approved nodes can partake in specific consensus roles.
* **Consensus Mechanism:** Stratos's combination of PoT and PoA creates a unique consensus model that balances decentralization and centralization. While PoT encourages active participation from all nodes, PoA limits the consensus process to a select group, centralizing the decision-making process to some extent.
* **Economic Model:** Stratos's economic model is centrally managed, with the team controlling the tokenomics and reward mechanisms. While nodes earn STOS tokens for contributing resources, the central team influences the overarching economic framework, which could limit the network's fully decentralized nature.
* **Network Evolution:** Stratos's evolution is guided by its core team, with updates and governance decisions likely controlled centrally. This approach contrasts with networks where a decentralized community drives changes and updates entirely through on-chain governance.
{% endtab %}

{% tab title="BZZ" %}
**Decentralization:** Level 4 (High decentralization and improving the network evolution decentralization)

**Review:** Swarm is a decentralized storage and communication platform that aims to provide a scalable and self-sustaining system for Web3. It is designed to function as the storage and distribution layer of the Ethereum Web3 stack, offering a robust, censorship-resistant infrastructure for decentralized applications (dApps).

**Network Structure and Consensus Mechanism:** Swarm operates on a decentralized node network that stores and serves content. The network uses the **Swarm Accounting Protocol (SWAP)** and a non-zk proof-of-storage mechanism to incentivize nodes to store and serve data. These protocols ensure that nodes are compensated for their services and that data is redundantly stored across the network, enhancing availability and reliability.

While Swarm employs decentralized technologies like PoSt, SWAP introduces a level of centralization. The network's reliance on specific economic incentives and the potential oversight in balancing these incentives suggests that while the data storage component is decentralized, other aspects of network management could be more centralized.

**Impact on Decentralization:** Swarm's approach to decentralization is multifaceted. While the storage and data-serving aspects are decentralized through a network of nodes, the overall governance and economic incentive structure introduce some centralized elements. The centralized oversight of the SWAP protocol and the need to balance incentives across the network might limit the extent of full decentralization.

**Level Evaluation:**

* **Service Providers:** In Swarm, service providers can deploy their applications on the network, benefiting from its decentralized storage and distribution capabilities.
* **Infrastructure Providers:** Nodes providing storage and bandwidth operate decentralizedly. The infrastructure provider can commit a node without considering a centralized vetting process.
* **Consensus Mechanism:** It relies on SWAP and PoSt, which decentralize storage and the consenus and the associated algorithms are extremely decentralized by design.
* **Economic Model:** The economic model of Swarms involves the distribution of rewards and penalties among nodes based on their participation and contribution to the network related to future-proof Storage.
* **Network Evolution:** The evolution of Swarm is likely guided by a core development team, with updates and governance decisions potentially being made centrally, although the community may have some input.
{% endtab %}

{% tab title="EMAID" %}
**Decentralization**: Level 3 (Moderate decentralization with improvements of network economy)

**Review:** The Safe Network, initially known as MaidSafeCoin, is an ambitious project aiming to create a fully decentralized and autonomous internet where data is stored, managed, and accessed without centralized servers or intermediaries. The Safe Network's primary focus is on data privacy, security, and freedom, aiming to provide users with complete control over their data in a decentralized manner.

**Network Structure and Consensus Mechanism:** The Safe Network operates through a distributed network of nodes, each contributing storage space, bandwidth, and processing power. The network’s data management is fully decentralized, employing a unique consensus mechanism known as **Proof of Resource** (PoR). This mechanism ensures that nodes (known as vaults) are rewarded based on the resources they provide to the network, such as storage space and CPU power.

**Impact on Decentralization:** The Safe Network achieves high decentralization in data storage and management. However, some aspects of the network’s governance and economic model were centrally controlled during its early development stages, which can be seen as a limitation in its overall decentralization.

**Level Evaluation:**

* **Service Providers**: In the Safe Network, service providers can freely deploy applications without interference from central authorities, ensuring a high level of decentralization for users and developers.
* **Infrastructure Providers**: Infrastructure providers (vault operators) have significant autonomy in the Safe Network. They contribute resources without requiring approval or oversight from a central entity, which aligns well with decentralized principles.
* **Consensus Mechanism**: The Proof of Resource mechanism is innovative and decentralized. It rewards nodes based on their contributions rather than requiring them to solve complex mathematical problems or hold significant stakes in the network.
* **Economic Model**: Initially, Safe Network’s economic model was centrally managed, with the MaidSafe team defining the distribution of rewards. However, as the network matures, the economic model is expected to evolve towards greater decentralization, with rewards and penalties being managed autonomously by the network.
* **Network Evolution**: The Safe Network’s development is driven by its core team, but it aims to transition to a more decentralized governance model as the network grows. This evolution could involve community-driven proposals and decisions being made through on-chain governance mechanisms.
{% endtab %}

{% tab title="SCP" %}
**Decentralization**: Level 2 (Low decentralization with centralization in governance and economic models)

**Review:**

ScPrime is a decentralized storage network that offers enterprise-grade solutions for secure and distributed data storage. The platform emphasizes cost-effectiveness and reliability, targeting both individual and enterprise users. Despite its decentralized storage model, ScPrime incorporates several centralized elements in its governance and economic models, which influence the overall decentralization of the network.

**Network Structure and Consensus Mechanism:** ScPrime operates through a network of decentralized storage nodes, where operators provide storage capacity in exchange for rewards in ScPrime tokens (SCP). The network uses a Proof-of-Storage mechanism to ensure that storage providers uphold their data storage commitments. This mechanism verifies that storage providers correctly store the data they commit to by requiring them to submit periodic proofs. Failure to provide these proofs results in penalties, ensuring data availability and encouraging honest participation. While the storage network is decentralized, ScPrime's governance is more centralized. The core development team and a limited set of trusted nodes control key decisions regarding network upgrades, economic policies, and other aspects of the network.

**Impact on Decentralization:** ScPrime's network exhibits both decentralized and centralized characteristics. The storage network is decentralized, with data distributed across various nodes, but the governance and economic models show centralization, particularly in decision-making and reward distribution.

**Level Evaluation:**

* **Service Providers**: Service providers can deploy applications that use ScPrime's decentralized storage network. However, the influence of centralized governance could impact how these services operate within the network.
* **Infrastructure Providers**: While node operators have autonomy in offering storage, their participation is governed by rules and policies set by the centralized development team. This introduces a layer of centralization, as operators must adhere to these rules to participate fully in the network.
* **Consensus Mechanism**: ScPrime’s consensus mechanism ensures decentralized storage verification, but the broader consensus and governance structures are less decentralized. The centralization of decision-making power within the core team and trusted nodes contrasts with networks that rely on fully decentralized consensus mechanisms.
* **Economic Model**: ScPrime's economic model is centrally managed. The core team defines the tokenomics and reward mechanisms, influencing how rewards are distributed across the network. This central control over the economic framework limits the degree of decentralization in the network.
* **Network Evolution**: ScPrime’s evolution is largely guided by its core team, with decisions on network updates and governance controlled centrally. This contrasts with networks where updates and changes are driven entirely by a decentralized community through on-chain governance.
{% endtab %}

{% tab title="CRU" %}
**Decentralization**: Level 3 (Low decentralization, but GPoS tends to centralize the economy model)

**Review:** Crust Network is a decentralized storage protocol designed to provide a decentralized cloud ecosystem that supports Web3.0 applications. Crust integrates a decentralized storage layer with a blockchain-based incentive layer, offering a comprehensive solution for storing and managing data across a distributed network of nodes. The network aims to provide a highly decentralized storage system while maintaining economic and operational efficiency.

**Network Structure and Consensus Mechanism:** Crust Network operates on a decentralized network of storage nodes, which provide storage capacity in exchange for CRU tokens, the network's native cryptocurrency. These nodes are incentivized to store and maintain data through the Meaning Proof-of-Work (MPoW), Guaranteed Proof-of-Stake (GPoS) and a decentralized storage mechanism similar to IPFS. Crust employs GPoS mechanism for ata storage, which combines traditional PoS with incentives for storage providers. This hybrid approach ensures that storage providers are rewarded based on their storage contributions while aso participating in network security through staking.

**Impact on Decentralization:** Crust Network exhibits high decentralization, particularly in its storage and economic models. However, some elements of centralization are present in the governance and decision-making processes.

**Level Evaluation:**

* **Service Providers**: Service providers can freely deploy their applications on the Crust Network, leveraging decentralized storage capabilities. The network is designed to be permissionless, allowing anyone to contribute storage resources without requiring approval from a central authority.
* **Infrastructure Providers**: Storage providers in Crust have significant autonomy, as they can join the network without centralized oversight.
* **Consensus Mechanism**: Crust's GPoS-based consensus mechanism ensures a decentralized approach to securing the network. However, the staking process introduces a layer of centralization, as validators' influence is proportional to their stake in the network. This could lead to centralization of power among large stakeholders.
* **Economic Model**: Crust's economic model is decentralized by design, with rewards distributed to storage providers and validators based on their contributions.
* **Network Evolution**: While Crust Network is highly decentralized in its operations, its core development team somewhat guides its network evolution. Governance decisions, including updates and network changes, are likely influenced by a centralized group, though community participation is encouraged through on-chain governance mechanisms.
{% endtab %}
{% endtabs %}
