# Unseal Procedure

The **Unseal** process in the Filecoin network is a crucial operation that involves decrypting and recovering data from a sealed sector. This process is necessary when a storage provider needs to retrieve a client’s stored data for retrieval purposes. Unsealing is computationally intensive, similar to sealing, as it reverses the cryptographic operations performed during the **PreCommit1 (PC1)** and subsequent stages. Let's break down the Unseal process, its technical intricacies, and its impact on the storage provider's operations.

## **Overview**

* **Purpose of Unsealing:**\
  Unsealing is required to access the original data stored within a **sealed sector**. Since sectors are sealed to prove unique storage via **Proof-of-Replication (PoRep)**, the original data is not directly accessible until the unseal operation is performed.
* **Reversing Cryptographic Securing:**\
  Unsealing reverses the cryptographic encoding applied during the sealing process (PC1, PC2). This involves decrypting and reconstructing the data from its sealed form, stored in a secure, compressed, and tamper-proof format.

## **Parameters and Environment Setup**

* **Cryptographic Parameters:**\
  The unseal process requires the same cryptographic parameters used during the sealing phases (PC1 and PC2). These parameters are retrieved from a cache stored on high-performance NVMe storage to ensure low-latency access.
* **CPU Requirements:**\
  Similar to the PC1 phase, unsealing is a **CPU-intensive** process. It benefits significantly from **multi-core CPUs** and architectures that support SHA256 and other cryptographic extensions. Unlike PC1, which is typically single-threaded, the unsealing process can often leverage multiple CPU threads to speed up data decoding.

## **Memory and Storage Utilization**

* **Data Reconstruction:**\
  Unsealing involves reading the sealed sector and reconstructing the original data using the encoded layers generated during the PC1 and PC2 phases. The entire data structure, including the Merkle tree and additional metadata, is processed to verify and reconstruct the original data.
* **Memory Consumption:**\
  The memory requirements for unsealing are substantial, but generally less than those for sealing. For a **32 GiB sector**, the memory footprint can range from **64 GiB to 128 GiB**, while for a **64 GiB sector**, it may be around **128 GiB to 256 GiB**. The exact requirements depend on the implementation and the specific cryptographic steps involved.

## **Process Execution**

* **Sequential Data Decoding:**\
  The unsealing process is performed sequentially, layer by layer, in reverse order from the sealing process. Each layer must be decoded and verified before proceeding to the next. This ensures that the data is correctly reconstructed without corruption or loss.
* **Concurrent Unseal Management:**\
  Similar to managing concurrent PC1 jobs, it is essential to control the number of concurrent unseal jobs to avoid overloading the system. The number of unseal jobs running in parallel can be managed by setting environment variables or configuring system resource management tools.

## **The 11 Layers of Data Decoding**

* **Layer Purpose:**\
  The 11 layers generated during the PC1 phase must be decoded in reverse to unseal the data. Each layer represents a step in the transformation process, from the deepest cryptographic encoding back to the original, human-readable form.
* **Technical Details:**\
  The decoding involves reversing hash functions and cryptographic transformations applied during sealing. Each layer is verified against the cryptographic proofs to ensure that the data being reconstructed matches the original client data.

## **Final Steps and Time Considerations**

* **Unsealing Time:**\
  The time to unseal a **32 GiB sector** typically takes about **2 to 4 hours**, depending on the server’s hardware specifications, workload, and the efficiency of the cryptographic operations. For **64 GiB sectors**, the time can be longer, up to **6 to 8 hours**. High-performance CPUs, fast storage (NVMe), and sufficient memory can significantly reduce these times.
* **Sealed Sector Handling Post-Unseal:**\
  After unsealing, the sector may be kept in its unsealed state for future access if frequent retrievals are expected, or it may be resealed to restore the sector's integrity and security. Resealing requires additional time and resources, and it is generally avoided unless necessary.

## **Optimization and Resource Management**

* **Balancing Sealing and Unsealing Operations:**\
  Storage providers need to balance sealing and unsealing operations to optimize system performance and minimize downtime. Effective scheduling of unseal tasks can help avoid bottlenecks, especially in environments where retrieval requests are frequent.
* **Client Satisfaction and Retrieval SLAs:**\
  Optimizing unsealing processes is crucial for meeting **Service Level Agreements (SLAs)** related to data retrieval times. Quick unsealing times translate to higher client satisfaction and more competitive services.
