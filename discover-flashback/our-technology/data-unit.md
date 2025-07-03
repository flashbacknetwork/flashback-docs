# Data Unit

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (20).jpg" alt=""><figcaption><p>This diagram represents the simplifed data unit submission workflow</p></figcaption></figure>

## **Data Unit: What is it?**

The data unit is not only a storage capacity or compute service offered by the provider but provides additional information such as the quality of services, the geographical location, and more. Each data unit supports multiple reservations (e.g., Reservation 1, Reservation 2, Reservation 3), which represent allocations made by consumers for specific data storage needs.&#x20;

This elementary reservation is to build a system where the user controls their expenses and their needs. At the same time, it ensures the Providers monitor more efficiently the security and the distribution of data in its infrastructure. By extension, this can enable Providers to supply unused capacity from their infrastructure.

### **Actions from Providers**

**Each provider has specific "Data Units,"** representing discrete storage capacities or compute services (e.g., S3-compatible, GCS-compatible, or other certified protocols). This elementary reservation is to build a system where the user controls their expenses and their needs. At the same time, it ensures the providers monitor more efficiently the security and the distribution of data in its infrastructure. **Providers submits their Data Units with the API of the Flashback DePin Platform** to make their services available for reservation. This offer will then be submitted in the smart contracts by waiting for the allocation by a Consumer.

## Consumers

Individuals, businesses, or applications requiring storage services rely on the **Scoring** system to select providers based on reliability, performance, and cost. Scoring ensures providers are ranked fairly and transparently based on their SLA compliance, and QoS metrics, but also from the quality report of consumers.&#x20;

Consumers can analyze the performances of providers with the QoS metrics and select what best fits them within the data units. They represent entities (businesses or users) utilizing the storage services provided by the platform.

A Light Node is installed on the consumer side to support the interactions with the platform.

***

## **Interactions Between Elements**

1. **Providers ↔ Orchestrator**:
   * Providers register data units and agree to SLAs managed by the Orchestrator. Based on performance, they receive scoring and incentives.
2. **Consumers ↔ Orchestrator**:
   * Consumers reserve storage and make payments via the Orchestrator, which ensures QoS and compliance with SLAs.
3. **Consumers ↔ Platform ↔ Providers**:
   * Through the platform, consumers directly interact with data units for file transfers and storage access.
4. **Tokenomics Layer**:
   * Integrated into the Orchestrator, it manages payments from consumers, rewards for providers, and penalties for non-compliance or failure. This is a long-term feature that we are improving currently in our development iterations.

