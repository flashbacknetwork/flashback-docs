# File Storage Deals

The deal and sectors are unitary elements that compose the Filecoin network. The Flashback network derives these components to support the data storage security.

## Deal: A file Storage Contract with the Network

In the Filecoin network, a "deal" refers to an agreement between a client and a storage provider. Essentially, this deal is a contract where the client pays the storage provider to keep their files securely on the network for a specified duration. The storage provider allocates space within its systems to house the client's data, ensuring its safety and availability as agreed upon in the terms of the deal.

### **Overview**

A file storage contract in the Filecoin network can be compared to a traditional service level agreement (SLA) in conventional cloud storage services but is enforced by blockchain technology. Here's how it typically works between a network client and a storage provider (it can be extended to multiple storage providers):

1. **Making a Deal:**
   * The client selects a storage provider and proposes a deal.
   * The deal proposal includes details such as the required storage size, duration, and price willing to be paid.
2. **Acceptance and Storage:**
   * If the storage provider agrees to the terms, they accept the deal.
   * The client then sends their data to the storage provider.
   * The provider stores the data and must periodically prove to the network that they are correctly storing it through cryptographic proofs.
3. **Deal Lifecycle:**
   * Deals in Filecoin are immutably recorded on the blockchain, creating a transparent and verifiable record of the agreement and its fulfillment.
   * Storage providers receive compensation in Filecoin tokens, which are disbursed according to the contract terms, typically after they successfully prove they are holding the data as agreed.
   * The minimum duration for these deals is 180 days, while the maximum extends to 540 days, balancing deal length with cryptographic security needs.
4. **Proofs of Storage:**
   * Throughout the deal, the storage provider must submit proof to the blockchain. These proofs, known as Proof-of-Spacetime (PoSt), verify that the data is correctly stored over time.
5. **Deal Completion:**
   * Upon completion of the deal term, the client can retrieve the data, or the deal can be renewed or extended.

Using smart contracts for these deals adds a layer of security and automation, reducing the potential for disputes and ensuring compliance with the agreed terms without requiring intermediaries.

The structure of Filecoin’s storage deals leverages blockchain technology to provide a decentralized, reliable service. This method democratizes access to data storage and enhances data sovereignty by giving clients control over their storage terms and conditions without relying on centralized entities.
