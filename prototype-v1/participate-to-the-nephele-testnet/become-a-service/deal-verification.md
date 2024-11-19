# ℹ️ Deal Verification

A **service gateway** (acting as a client) in Filecoin can verify the proof of a deal to ensure that the storage provider is genuinely storing the data as agreed and can also verify the integrity of the data when it is retrieved to ensure it has not been tampered with. Here’s how these verifications work:

## **Verifying the Proof of a Deal**

### **With Proof-of-Replication (PoRep)**

* The **Proof-of-Replication (PoRep)** is generated when a storage provider seals data into a sector. It cryptographically proves that the storage provider has created a unique replica of the data and is storing it as agreed.
* **On-Chain Verification:**
  * The **PoRep** is submitted on-chain during the deal's commitment phase. The service gateway (client) can verify this proof on-chain using the Filecoin blockchain explorer or directly by querying the blockchain. The proof is generated using zero-knowledge proofs (zk-SNARKs), ensuring it is valid without revealing the actual data.
* **Proof Validation:**
  * The service gateway can use the information stored on-chain to verify that the storage provider has sealed the data correctly. The on-chain records show the sector's commitments, cryptographic proofs, and deal parameters.

### **With Proof-of-Spacetime (PoSt)**

* Storage providers periodically generate the **Proof-of-Spacetime (PoSt)** to prove that they are continuously storing the data over time.
* **Windowed PoSt Verification:**
  * The service gateway can verify that the storage provider submits regular **Windowed PoSts** as the Filecoin protocol requires. These proofs are also submitted on-chain and are publicly accessible.
* **Checking PoSt Submissions:**
  * By checking the blockchain records, the service gateway can see if the storage provider has regularly submitted PoSts for the sectors where their data is stored, ensuring ongoing compliance and storage integrity.

## **Verifying the Data Upon Retrieval**

* **Content Identifier (CID) Verification:**
  * When the service gateway uploads data to the storage provider, a **Content Identifier (CID)** is generated based on the **Merkle DAG (Directed Acyclic Graph)** structure of the data. This CID is a cryptographic hash that uniquely represents the data.
  * **Verification of Data Integrity Using CID:**
    * When the service gateway retrieves the data, it can recompute the CID of the retrieved data and compare it with the original CID generated upon uploading.
    * If the computed CID matches the original CID, it proves that the data retrieved is the same as the data that was originally uploaded, confirming that it has not been tampered with or altered.
* **Merkle Proof Verification:**
  * Filecoin uses **Merkle Trees** to organize data within sectors. Each piece of data (or chunk) has a corresponding **Merkle Proof** that can be used to verify its inclusion in the sector without revealing all the data.
  * **How to Verify with Merkle Proofs:**
    * Upon data retrieval, the service gateway can request a **Merkle Proof** from the storage provider that shows the retrieved chunk's position in the Merkle Tree.
    * By verifying the Merkle Proof against the **Merkle Root** stored on-chain, the service gateway can confirm that the data is part of the original stored data, ensuring its integrity.
