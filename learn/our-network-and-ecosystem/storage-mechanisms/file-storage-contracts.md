# Deal and Sectors

The deal and sectors are unitary elements that compose the Filecoin network. The Flashback network derives these components to support the data storage security.

## Deal: A file Storage Contract with the Network

In the Filecoin network, a "deal" refers to an agreement between a client and a storage provider. Essentially, this deal is a contract where the client pays the storage provider to keep their files securely on the network for a specified duration. This process involves the storage provider allocating space within their systems to house the client's data, ensuring its safety and availability as agreed upon in the terms of the deal.

### **File Storage Contract Overview**

A file storage contract in the Filecoin network can be compared to a traditional service level agreement (SLA) in conventional cloud storage services but is enforced by blockchain technology. Here's how it typically works between a network client and a storage provider (it can be extended to multiple storage providers):

1. **Making a Deal:**
   * The client selects a storage provider and proposes a deal.
   * The deal proposal includes details such as the storage size required, the storage duration, and the price willing to be paid.
2. **Acceptance and Storage:**
   * If the storage provider agrees to the terms, they accept the deal.
   * The client then sends their data to the storage provider.
   * The provider stores the data and must periodically prove to the network that they are correctly storing it through cryptographic proofs.
3. **Deal Lifecycle:**
   * Deals in Filecoin are immutably recorded on the blockchain, creating a transparent and verifiable record of the agreement and its fulfillment.
   * Storage providers receive compensation in Filecoin tokens, which are disbursed according to the contract terms, typically after they successfully prove they are holding the data as agreed.
4. **Proofs of Storage:**
   * Throughout the deal, the storage provider must submit proof to the blockchain. These proofs, known as Proof-of-Spacetime (PoSt), verify that the data is correctly stored over time.
5. **Deal Completion:**
   * Upon completion of the deal term, the client can retrieve the data, or the deal can be renewed or extended.

Using smart contracts for these deals adds a layer of security and automation, reducing the potential for disputes and ensuring compliance with the agreed terms without requiring intermediaries.

The structure of Filecoin’s storage deals leverages blockchain technology to provide a decentralized, reliable service. This method democratizes access to data storage and enhances data sovereignty by giving clients control over their storage terms and conditions without relying on centralized entities.



## Sectors: Split Hardware to Atomic Element for Better Proving

In the Filecoin network, a "sector" is a fundamental unit of storage that a storage provider commits to the network to use in deals with clients. Essentially, sectors are how storage is organized and sold in Filecoin. Here’s a breakdown of what a sector involves and its role in the network:

### Definition and Purpose

* **Size and Configuration**: Sectors are defined by the Filecoin protocol. Common sizes are 32 GiB ([gibibytes](https://www.techtarget.com/searchstorage/definition/gibibyte-GiB)) and 64 GiB. The size determines how much data can be stored in a single sector.
* **Commitment to the Network**: Storage providers commit these sectors to the Filecoin blockchain through a process known as "sealing." Sealing is a cryptographic process that prepares the sector for storage by encoding the data and generates proofs of replication (PoRep) to prove that the data is uniquely stored.

### Role in Filecoin

* **Storage Deals**: When a client and a storage provider agree on a storage deal, the data is stored in one or more sectors. Each sector is dedicated to a particular deal or could be shared among multiple deals, depending on the agreement and the sector size.
* **Proving Storage**: Sectors are critical for storage providers to prove that they reliably store data. Providers must submit regular proofs, known as Proofs of Spacetime (PoSt), which attest that each committed sector is correctly storing its data over time.
* **Lifecycle**: A sector's lifecycle in Filecoin includes pledging (committing the sector), sealing (preparing and proving the storage of data), storing (the duration of the storage deal), and, eventually, sector removal or re-use after a deal concludes.

### Importance

Sectors are crucial because they not only organize how data is stored in the Filecoin network but also underpin the network’s integrity and trust model. By requiring storage providers to commit sectors and regularly prove their correct storage, Filecoin ensures that the network remains secure and that data is stored as agreed upon in contracts.
