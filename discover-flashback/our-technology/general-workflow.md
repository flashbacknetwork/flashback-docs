# General Workflow

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (4).jpg" alt=""><figcaption><p>This diagram represents the simplifed general workflow</p></figcaption></figure>

## **Orchestrator Smart Contract**

It acts as the central coordinating unit for managing providers, consumers, and their interactions. The role of the smart contract is to guarantee the commitments of the service-level agreements (SLA) and their assessment over time. The smart contract will hold the payment balance specifically for the providers bringing their storage infrastructure into the platform. See more [here](orchestrator.md).

***

## **Providers**

Each provider has specific "Data Units," representing discrete storage capacities or compute services (e.g., AWS S3 buckets, Azure Blob Storage, or Custom Functions). This elementary reservation is to build a system where the user controls their expenses and their needs. At the same time, it ensures the providers monitor more efficiently the security and the distribution of data in its infrastructure.

Providers register their data units with the Orchestrator Smart Contract to make their services available for reservation. The data unit is not only a storage capacity or compute service offered by the provider but provides additional information such as the quality of services, the geographical location, and more. Each data unit supports multiple reservations (e.g., Reservation 1, Reservation 2, Reservation 3), which represent allocations made by consumers for specific data storage needs. The **Orchestrator tracks these reservations** and ensures they align with SLA terms.

***

## **API in Flashback Platform**

The API serves as the interface for communication between the smart contract, the provider, and the consumers. It allows consumers to query available data units, reserve storage, and interact with providers directly and provides a standardized way for applications and services to interact with the platform. See more [here](api-service.md).

***

## Consumers

Individuals, businesses, or applications requiring storage services rely on the **Scoring** system to select providers based on reliability, performance, and cost. Scoring ensures providers are ranked fairly and transparently based on their SLA compliance, and QoS metrics, but also from the quality report of consumers. This unique feature allows for a fair and clear understanding of providers' quality, a fundamental component of incentivizing the quality of services.

Additionally, consumers can analyze the Flashback network and the performances of providers with the QoS metrics and select what best fits them within the data units. They represent entities (businesses or users) utilizing the storage services provided by the platform.

* **Applications**:
  * Applications connect to the API to manage their storage needs.
  * Apps can reserve data units and interact with multiple providers through the API.
* **Interaction with Orchestrator**:
  * Consumers rely on the Orchestrator to ensure service quality, track payments, and manage disputes.

***

## **Interactions Between Elements**

1. **Providers ↔ Orchestrator**:
   * Providers register data units and agree to SLAs managed by the Orchestrator. Based on performance, they receive scoring and incentives.
2. **Consumers ↔ Orchestrator**:
   * Consumers reserve storage and make payments via the Orchestrator, which ensures QoS and compliance with SLAs.
3. **Consumers ↔ API ↔ Providers**:
   * Through the API, consumers directly interact with data units for file transfers and storage access.
4. **Tokenomics Layer**:
   * Integrated into the Orchestrator, it manages payments from consumers, rewards for providers, and penalties for non-compliance or failure. This is a long-term feature that we are improving currently in our development iterations.

