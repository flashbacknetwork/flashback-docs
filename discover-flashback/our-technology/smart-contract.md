# Smart Contract

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (1).jpg" alt=""><figcaption><p>A logic scheme of our orchestrator within the Flashback network</p></figcaption></figure>

The image represents the principle logic integrating into the smart contracts acting as an on-chain and trustless orchestrator for our network. The **Orchestrator Smart Contract** is the backbone of the ecosystem, ensuring transparency, compliance, and fair financial transactions through tokenomics. It is critical in maintaining trust and reliability between providers and consumers.&#x20;

The orchestrator will be deployed on other blockchains and other promising ecosystems. This multi-chain approach allows storage providers and clients to select the ecosystem they prefer and to optimize their costs and performances by balancing with the networks' load.

Here is the list of supported ecosystems:

* Stellar (testnet),
* Starknet (PoC).

***

## **Management of Payments**

The smart contract is the best decentralized technology to support payments and other escrow-like services. In Flashback, we decided to use it for payment management, traceability and compliance reasons. It manages the financial and operational aspects of the ecosystem, including:

* **Escrow**: Holds payments securely until conditions in the Service Level Agreements (SLAs) are fulfilled. SLAs must properly specify the conditions of payments, and the Flashback platform allows for the best agreements.
* **Pricing**: Determines the cost of services, ensuring fairness and market-driven adjustments. Providers must dynamically adapt their pricing according to their resources and services. The integration of AI-driven pricing mechanisms is recommended, and Flashback will propose some of them.
* **Slashing:** Penalizes data providers or consumers who violate SLAs or fail to meet quality standards. This mechanism is essential to guaranteeing a healthy ecosystem. Meanwhile, the Flashback platform will be a possible provider intermediary to solve disputes.

***

## **More About Data Units**

Data units represent the storage resources (e.g., storage servers or systems) managed by the data providers. Like the sectors in Filecoin, the providers will commit their available spaces with the QoS specifications attached to every data unit. Data units are tracked and managed via reservations, ensuring efficient allocation and availability. There are 4 different states for a data unit:

* **Reserved**: Data sector allocated but not yet in use. It allows the storage providers to allocate and support the best quality of services. The storage providers may still decide on the allocation for a user, and then, have the freedom of doing the best business.
* **In Use**: This state means it is actively storing data for users.
* **Maintenance**: Undergoing updates or repairs of the data unit which is fundamental to ensure a good quality of services.
* **Decommissioning**: Being removed from the active pool of resources. This state is mainly because the smart contract is memorizing all the data units and then, the decommissioning is needed to not use the data unit again.

***

## **Interactions**

1. **Storage Providers ↔ SLAs ↔ Orchestrator**:
   * Providers register their resources and agree to SLAs enforced by the orchestrator.
   * QoS metrics are monitored to ensure compliance and penalties (slashing) are applied for breaches.
2. **Users ↔ Scoring ↔ Orchestrator**:
   * Users use the scoring system to select reliable providers.
   * Payments are handled via the payment module (escrow ensures funds are secure until SLAs are fulfilled).
3. **Orchestrator ↔ Data Units**:
   * The orchestrator tracks and manages data units through their lifecycle (reserved, in use, maintenance, decommissioning).
   * Ensures optimal resource utilization and availability for users.
