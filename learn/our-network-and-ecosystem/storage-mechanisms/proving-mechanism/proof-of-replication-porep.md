# Initial Sealing (PoRep)

**Proof of Replication (PoRep)** is a mechanism by which a storage provider proves to the network that data has been replicated to its unique copy. <mark style="color:orange;">**PoRep happens when the data is first sealed and stored**</mark><mark style="color:orange;">.</mark> When a storage provider in the Filecoin network stores client data, the data is first placed into a sector and then sealed through a cryptographic process to ensure data integrity and confidentiality. A unique encoding is generated as proof of storage, which is then compressed and submitted to the network to certify that the data is securely stored according to the agreed terms. You can find a mathematical approach [here](https://filecoin.io/proof-of-replication.pdf).

The unique encoding generated during the sealing process in Filecoin is based on the data being stored, the storage provider's identity, and the sealing timestamp. This encoding is highly sensitive to changes in any of these elements, ensuring that the proof is unique, tamper-evident, and reliably verifies that the provider stored the specific data at a given time.



***

This cryptographic approach ensures that all stored data is secure and verifiable, maintaining trust and integrity within the Filecoin network. This process underscores the robustness of Filecoin's security measures, designed to safeguard client data against tampering and ensure compliance with storage agreements. By understanding every step of PoRep, let's explore how Filecoin guarantees a received file is verified and marked with its proof.
