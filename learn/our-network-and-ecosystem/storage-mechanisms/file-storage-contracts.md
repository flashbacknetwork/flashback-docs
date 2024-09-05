# Storage Deals

A **storage deal** in the Filecoin network represents a service agreement between a **client** and a **storage provider** (SP), facilitated and enforced by blockchain technology. The lifecycle of a deal involves several phases, ensuring data integrity, availability, and fair compensation for the storage provider.

## **1. Initiating a Deal**

* **Proposal Submission**: The lifecycle of a deal begins when a client proposes a deal to a storage provider. The proposal includes details such as the required storage size, the duration of storage (minimum of 180 days to a maximum of 540 days), and the price the client is willing to pay for storage services.
* **Deal Negotiation**: The storage provider reviews the proposed deal terms. If they find them acceptable in terms of price, duration, and data requirements, they accept the deal.

## **2. Data Transfer and Storage Commitment**

* **Data Transfer**: Once the storage provider accepts the deal, the client transfers their data to the provider. This data is typically uploaded in a format that the Filecoin network supports, such as a CAR (Content Addressable aRchive) file.
* **Sealing Process**: Upon receiving the data, the storage provider begins the process of sealing. Sealing is a cryptographic process that transforms the raw data into a "sealed" format using Proof-of-Replication (PoRep). This process ensures the data is uniquely stored and replicated by the provider.

## **3. Deal Expiry and Post-Term Actions**

* **Deal Expiry**: As the deal reaches the end of its agreed duration, several options are available:
  * **Data Retrieval**: The client can retrieve their data from the storage provider before the deal expires. This retrieval process involves sending a request to the storage provider and receiving the data back in the agreed format.
  * **Deal Renewal or Extension**: If the client requires continued storage, they can negotiate a new deal with the provider to extend the storage duration. This would involve proposing a new set of terms, similar to the initial deal proposal phase.
  * **Sector Expiry**: If no renewal is negotiated and the client does not retrieve the data, the sealed sector will eventually expire. The provider may unseal the sector and reclaim the storage capacity for new deals or commitments.
* **Post-Deal State**: Once the sector expires and is no longer required for an active deal, the storage provider can either clear the storage space for new clients or retain the data based on their storage strategy.

## **4. On-Chain Records and Security**

* **Immutable Record-Keeping**: Every step of the deal lifecycle, from proposal to completion, is immutably recorded on the Filecoin blockchain. This provides a transparent and verifiable history of the agreement and its fulfillment, ensuring both parties adhere to the contract terms without requiring a central intermediary.
* **Smart Contract Automation**: The use of smart contracts in Filecoin ensures that the terms of the deal are automatically enforced, minimizing potential disputes and reducing the need for third-party arbitration. The blockchain's immutable nature guarantees that any network participant securely stores and verifies all actions and proofs.
