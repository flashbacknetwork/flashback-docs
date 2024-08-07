# Proof of Replication (PoRep)

Proof of Replication (PoRep) is a mechanism by which a storage provider proves to the network that data has been replicated to its unique copy. <mark style="color:orange;">**PoRep happens when the data is first sealed and stored**</mark><mark style="color:orange;">.</mark> The process involves the storage provider generating a unique data encoding, proving it is stored, and ensuring its retrievability. This proof ensures that the storage provider can only claim to store multiple copies of the data after actually doing so. Let’s clarify the process with more precision:

## The General Steps

1. **Data Placement**: When a storage provider agrees to store data for a client, the data is first placed into a storage sector. A sector is a designated storage unit within the storage provider's system.
2. **Sealing the Sector**: The storage provider then seals the sector. Sealing is a cryptographic process that involves encoding the sector's data to protect and prepare it for storage. This process transforms the data to ensure its integrity and confidentiality.
3. **Generating Unique Encoding**: During the sealing process, a unique encoding of the data is generated. This encoding acts as a cryptographic proof, verifying that the storage provider has replicated and stored the data as agreed.
4. **Compression of the Proof**: Once the unique encoding is created, it is compressed to optimize storage and transmission efficiency.
5. **Certification Submission**: The compressed proof is then submitted to the Filecoin network. This acts as a certification from the storage provider, confirming that the data has been securely stored according to the agreed terms.

These different steps will be explained in deeper details in the&#x20;

## Sealing as Proof

The unique encoding generated during the sealing process is derived from several crucial elements:

* **The Data**: The actual data being stored.
* **The Storage Provider**: It is responsible for sealing the data.
* **The Timestamp**: The specific time at which the data was sealed.

This encoding is highly sensitive to changes; any alteration in the data, the storage provider's identity, or the sealing time will result in a different encoding. This sensitivity ensures that the encoding is unique and tamper-evident, providing a reliable method to verify that a particular storage provider did store the specified data at a given time.

This cryptographic approach ensures that all stored data is secure and verifiable, maintaining trust and integrity within the Filecoin network. This process underscores the robustness of Filecoin's security measures, designed to safeguard client data against tampering and ensure compliance with storage agreements.

