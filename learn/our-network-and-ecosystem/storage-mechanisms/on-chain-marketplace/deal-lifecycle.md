# Deal Lifecycle

Every step of the deal lifecycle, from proposal to completion, is immutably recorded on the Filecoin blockchain. This provides a transparent and verifiable history of the agreement and its fulfillment, ensuring both parties adhere to the contract terms without requiring a central intermediary.

The use of smart contracts in Filecoin ensures that the terms of the deal are automatically enforced, minimizing potential disputes and reducing the need for third-party arbitration. The blockchain's immutable nature guarantees that any network participant securely stores and verifies all actions and proofs.

### **Deal Negotiation (Off-chain)**

* **Initiation**: Clients and storage providers begin by negotiating terms such as the size of the data, price, duration of storage, and specific storage requirements.
* **Deal Terms**: These are discussed off-chain to speed up the process and reduce transaction costs. Once both parties agree, they proceed to formalize the deal on-chain. It can be done manually, but deal-making systems exist to automate the process.&#x20;

### **Deal Setup (On-chain)**

* **AddBalance**: Both parties deposit FIL (Filecoin tokens) into the Storage Market Actor—a smart contract that manages deal transactions on Filecoin.
* **Publishing the Deal**: The client or provider then sends a message to the Storage Market Actor to publish the deal on the blockchain. This message includes the deal terms and the data's cryptographic hash as proof of the data that will be stored. The terms include details such as the required storage size, the duration of storage (a minimum of 180 days to a maximum of 540 days), and the price the client is willing to pay for storage services.

### **Data transfer**

* **Data Encryption (Off-chain):** Before sending the data to the storage providers and all the selected nodes, it is highly recommended that the client verify the transfer protocol's data encryption according to the level of security and privacy. While the sealing encrypts data automatically in a sector, the storage node receives the data "as it is" before doing this process.&#x20;
* **Data Transfer**: Once the storage provider accepts the deal, the client transfers their data to the provider. This data is typically uploaded in a format that the Filecoin network supports, such as a CAR (Content Addressable aRchive) file. If the node supports other protocols, the client will interact with these protocols thanks to the software's API.&#x20;

### Sealing Procedure

* **Data Aggregation**: The storage provider must seal data pieces of 32GiB or 64 GiB. When a file is received and costs are optimized, the storage provider will aggregate different deals to complete at the best sector size.
* **Sealing**: Upon receiving the data, the storage provider begins the process of [sealing](../proving-mechanism/proof-of-replication-porep.md).

### Sealing Procedure and Retrieval

* **Data Aggregation**: The storage provider must seal data pieces of 32GiB or 64 GiB. When a file is received, and costs are optimized, the storage provider will aggregate different deals to complete at the best sector size.
* **Sealing**: Upon receiving the data, the storage provider begins the process of [sealing](../proving-mechanism/proof-of-replication-porep.md).
* **Data Retrieval**: The client can retrieve their data from the storage provider before the deal expires. This retrieval process involves sending a request to the storage provider and receiving the data in the agreed format. The selection of storage providers that handle the risks related to the sealing process is essential.&#x20;

### **Deal Expiry and Post-Term Actions**

* **Deal Expiry**: As the deal reaches the end of its agreed duration, several options are available:
  * **Deal Renewal or Extension**: If the client requires continued storage, they can negotiate a new deal with the provider to extend the storage duration. This would involve proposing a new set of terms, similar to the initial deal proposal phase.
  * **Sector Expiry**: If no renewal is negotiated and the client does not retrieve the data, the sealed sector will eventually expire. The provider may unseal the sector and reclaim the storage capacity for new deals or commitments.
* **Post-Deal State**: Once the sector expires and is no longer required for an active deal, the storage provider can either clear the storage space for new clients or retain the data based on their storage strategy.
