# API Interactions

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (25).jpg" alt=""><figcaption><p>The Interactions with the Standard API module of the Flashback Platform</p></figcaption></figure>

## **Oracles**

The oracles bridge on-chain and off-chain data that provides real-time information to the smart contract (e.g., data integrity checks, usage statistics, pricing updates). It acts as a trusted intermediary for verifying the status and quality of data services provided. Oracles feed critical data to the Orchestrator to ensure informed decision-making and execution of smart contract logic.

***

## **Standard API**

A gateway facilitating communication between data providers, consumers, and the Orchestrator.

* **Components**:
  * Provide tools for data consumers and their applications to access and utilize the services offered by providers.
* **Interaction**:
  * Client libraries enable consumer apps to interact with the microservices.
* **Providers**:
  * Connect to the Standard API via the Client Libraries to register services, manage storage units, and handle consumer requests.
  * Orchestrator ensures providers meet quality and performance standards through real-time Oracle updates.
* **Users (Services):**
  * **Components:**  There are applications built on the Client Libraries, enabling users to interact with the platform. The API is vital for this application to work smoothly and seamlessly with the platform as Flashback will manage the updates and integrations of future Cloud components. The apps will serve end-users, representing the final point of interaction and the business model associated with the service of the users.
  * **Interaction:** Use the Client Libraries to interact with the Standard API to select and to pay the Data Units and other microservices. Then, interact directly with the&#x20;

***

## **Interactions Between Layers**

1. **Providers ↔ API ↔ Orchestrator**:
   * Providers register their data units via Client Libraries.
   * The Orchestrator ensures services' availability, compliance, and quality, with Oracles feeding real-time data.
2. **Consumers ↔ API ↔ Orchestrator**:
   * Consumers interact with the Open API via Client Libraries to select and pay storage services.
   * The Orchestrator manages payments, QoS enforcement, and disputes.
3. **Oracles ↔ Orchestrator ↔ API**:
   * Oracles provide the Orchestrator with validated off-chain data (e.g., QoS metrics, pricing, and storage status).
   * The Orchestrator ensures this data is accurately reflected in the API for both Providers and Consumers.
