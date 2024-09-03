# Storage Deals

A "deal" refers to an agreement between a client and a storage provider. Essentially, this deal is a contract where the client pays the storage provider to keep their files securely on the network for a specified duration. The storage provider allocates space within its systems to house the client's data, ensuring its safety and availability as agreed upon in the terms of the deal.

## **Overview**

A storage contract through a deal can be compared to a traditional service level agreement (SLA) in conventional cloud storage services but is enforced by blockchain technology. Here's how it typically works between a network client and a storage provider (it can be extended to multiple storage providers):

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

***







***

## Obtain the Proof of a Specific Contract

To determine the proof of a specific file within a sector in Filecoin, you need to understand that Filecoin does not directly produce proofs for individual files. Instead, it generates proofs for entire sectors containing potentially multiple files. However, you can indirectly verify the integrity and presence of a specific file within a sealed sector by leveraging Merkle trees and Content Identifiers (CIDs).

1. **Merkle Trees and Sector Structure**:
   * When a sector is sealed, Filecoin uses a Merkle tree to hash all the data within that sector. Each file or piece of data contributes to the leaves of the Merkle tree.
   * The root of this Merkle tree is included in the proof for the sector (e.g., during **Proof of Replication (PoRep)** and **Proof of Spacetime (PoSt)**).
   * To verify a specific file's presence within a sector, you need the Merkle proof path (a series of hashes) from the file's hash up to the root of the Merkle tree.
2. **Content Identifiers (CIDs)**:
   * Files stored in the Filecoin network are referenced by **Content Identifiers (CIDs)**, which are unique cryptographic hashes that represent the content of the file. When a file is added to a sector, its CID is one of the leaves in the Merkle tree.
   * To verify that a file exists in a sector, you compare the file's CID against the Merkle tree's structure and proofs.
3. **Verification Steps**:
   * **Step 1**: Retrieve the **CID** of the file you want to verify. This CID is generated when the file is initially added to the Filecoin network and represents the file's hash.
   * **Step 2**: Obtain the **Merkle proof** from the storage provider for the sector that contains your file. This proof includes all the hashes needed to compute the path from your file's hash (CID) to the Merkle root of the sector.
   * **Step 3**: Compute the Merkle root using the proof provided. If the computed Merkle root matches the sector's Merkle root included in the sector's **PoRep** or **PoSt**, you can be confident that the file is part of that sector and has been correctly stored.
4. **Proof-of-Inclusion Tools**:
   * In practice, there are tools and libraries that can help users verify file inclusion in a sector, often using cryptographic libraries for Merkle tree validation. Storage providers or third-party services may provide interfaces to help users generate or verify these proofs.

