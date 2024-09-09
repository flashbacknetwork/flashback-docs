# The List of Clients

S**torage clients** in Filecoin are software tools and libraries that allow users and developers to interact with the Filecoin network to manage storage and retrieval deals, store data, retrieve data, and participate in the decentralized storage ecosystem. These clients implement the Filecoin protocol and provide various functionalities for different types of users, including storage providers, developers, and end-users.

Storage software clients enable users to leverage Filecoin's decentralized storage capabilities by providing the necessary interfaces and tools to interact with the network's actors (like Market Actor, Storage Miner Actor, etc.), manage deals, verify proofs, and handle data storage and retrieval operations. Below are some of the prominent storage software clients that implement and use Filecoin:

{% tabs %}
{% tab title="Lotus" %}
Lotus is the most widely used and officially supported Filecoin client developed by Protocol Labs. It is the primary implementation of the Filecoin protocol and is written in **Go**.

* **Features:**
  * Implements the full Filecoin node capabilities, including storage miner operations, blockchain synchronization, deal-making, proof generation, and network participation.
  * Supports both **full nodes** (that store the entire blockchain and participate in consensus) and **light nodes** (with limited blockchain data).
  * Provides a **command-line interface (CLI)** and **HTTP API** for managing storage and retrieval deals, sector management, and wallet operations.

**Usage:** Lotus is primarily used by storage providers (miners), developers, and infrastructure operators who want to run their own Filecoin nodes or participate in mining.
{% endtab %}

{% tab title="FVM Clients" %}
The **Filecoin Virtual Machine (FVM)** allows developers to build and deploy smart contracts (also known as "actors") on the Filecoin blockchain. FVM clients are emerging storage clients that provide capabilities to interact with smart contracts and manage data and storage deals using programmable logic.

* **Features:**
  * Supports smart contract deployment and interaction using **WASM (WebAssembly)**.
  * Integrates with existing storage clients like **Lotus** for seamless interaction with the Filecoin blockchain and storage market.

**Usage:** Used by developers to build decentralized applications (dApps) on Filecoin, focusing on programmable storage logic, data marketplaces, and custom deal management.
{% endtab %}

{% tab title="Boost" %}
**Boost** is an advanced deal-making client designed to streamline and automate storage deal processes for storage providers. It is specifically optimized for **high-volume deal flow** and **automated deal negotiation**.

* **Features:**
  * Provides a user-friendly interface for storage providers to manage incoming storage deals, pricing, and market strategies.
  * Offers **automated deal acceptance**, negotiation, and management capabilities based on predefined rules and pricing policies.

**Usage:** Used by storage providers who want to optimize their deal-making process, reduce manual intervention, and handle large volumes of storage deals efficiently.
{% endtab %}

{% tab title="Powergate" %}
**Powergate** is a storage client developed by Textile that offers a higher-level abstraction over the Lotus client. It integrates IPFS (InterPlanetary File System) with Filecoin to provide a unified interface for decentralized storage.

* **Features:**
  * Combines IPFS and Filecoin to allow users to **pin data to IPFS** while storing it redundantly on Filecoin, ensuring both **retrievability** and **permanence**.
  * Offers a **REST API** and **gRPC** interface for developers to interact with the Filecoin network and manage data storage and retrieval.
  * Manages deal renewals, replication strategies, and automated storage management policies.

**Usage:** Used by developers and applications that want to leverage both IPFS and Filecoin for decentralized storage solutions, particularly when combining permanent storage with fast retrieval.
{% endtab %}

{% tab title="Estuary" %}
**Estuary** is a storage client that provides a user-friendly platform for storing large datasets on the Filecoin network. It abstracts away much of the complexity involved in managing storage deals.

* **Features:**
  * Provides a **web-based UI** and **API** for users to upload and manage their files on Filecoin.
  * Handles deal-making, retrieval, and replication automatically, allowing users to focus on their data without worrying about underlying deal management.

**Usage:** Targeted at users and organizations looking for a straightforward way to interact with Filecoin without deep technical knowledge of the underlying protocol.
{% endtab %}

{% tab title="Slate" %}
**Slate** is a user-friendly, open-source storage client built on top of Filecoin and IPFS. It provides a simple interface for storing, sharing, and managing files in a decentralized manner.

* **Features:**
  * Provides an intuitive web-based interface for uploading and managing files.
  * Seamlessly integrates with Filecoin and IPFS to provide both decentralized storage and fast data retrieval.

**Usage:** Used by end-users and developers who want a simplified way to manage their data storage on Filecoin without dealing with the complexities of deal-making or running full nodes.
{% endtab %}

{% tab title="Filecoin Station" %}
**Filecoin Station** is a desktop application for end-users that provides an easy way to interact with the Filecoin network, manage wallets, and participate in storage and retrieval deals.

* **Features:**
  * Offers a **user-friendly desktop interface** to interact with Filecoin, manage wallets, and store/retrieve files.
  * Supports integration with other Filecoin clients, providing a comprehensive ecosystem for interacting with the Filecoin network.

**Usage:** Targeted at casual users, content creators, and developers who want to explore the Filecoin network and interact with its storage ecosystem.
{% endtab %}
{% endtabs %}

Filecoin offers a variety of **storage software clients** that cater to different needs, from running full storage nodes with Lotus and advanced deal management with Boost, to building dApps with FVM clients and providing higher-level abstractions with Powergate and Estuary. These clients implement the Filecoin protocol and provide various interfaces, APIs, and tools to manage storage deals, data retrieval, and storage optimization, enabling a diverse ecosystem for decentralized storage solutions.
