# PreCommit 1 (PC1)

PreCommit 1 (PC1) is a critical and resource-intensive phase in the Filecoin sealing pipeline. It primarily involves the cryptographic securing of data within a sector and is foundational in preparing the data for long-term storage on the Filecoin network. Let's break down the PC1 process, including a closer look at the 11 layers of data encoding it involves.

## Overview

**Cryptographic Securing**: In PC1, each sector—whether it already contains data or not—is cryptographically transformed using Proof-of-Replication (PoRep). This involves encoding the data in such a way that proves the storage provider (SP) is uniquely storing the client's data.

### **Parameters and Environment Setup**:

* **Cryptographic Parameters**: The process begins with loading cryptographic parameters from a cache. These parameters are essential for the encoding process and are stored on enterprise-level NVMe storage to minimize latency.
* **CPU Requirements**: PC1 is executed as a single-threaded process that is heavily reliant on CPU capabilities, particularly those that support SHA256 extensions. Optimal CPUs for this task include AMD Epyc Milan/Rome and Intel Xeon Ice Lake processors with 32 cores or more.

### **Memory and Storage Utilization**:

* The data for each sector is processed to create multiple layers of encoded data. Specifically, PC1 generates 11 layers for each sector.
* **Memory Consumption**: The scratch space required for a 32 GiB sector is approximately 384 GiB, and for a 64 GiB sector, around 768 GiB. This expansive use of scratch space is due to the need to manage multiple encoded versions of the data simultaneously.

### **Process Execution**:

* To ensure the sealing pipeline operates efficiently without overloading the system, it's crucial to manage the number of concurrent PC1 jobs. This is typically controlled by setting the `PC1_32G_MAX_CONCURRENT` environment variable, limiting simultaneous encoding jobs per server.

## The 11 Layers of Data Encoding

During the PC1 phase, 11 distinct data layers are created as part of the sector encoding process. Here’s a generalized overview of what these layers represent:

* **Layer Purpose**: Each layer serves as a step in the transformation process, enhancing the data's security and ensuring it is stored non-duplicable.
* **Technical Details**: The layers are generated through a series of hash functions and encoding steps, collectively building a complex and secure representation of the original data. This multi-layered approach not only secures the data but also prepares it for the generation of a unique replication proof.

## **Final Steps and Time Considerations**

* **Sealing Time**: The duration to seal a single 32 GiB sector typically takes about 3 hours, although this can vary based on the server’s hardware specifications and the workload of other tasks being processed simultaneously.

By understanding and optimizing each component of PC1, storage providers can significantly enhance their operational efficiency and ensure compliance with the Filecoin network's security standards. This detailed setup not only helps in managing the computational load but also aligns with Filecoin’s requirements for data integrity and proof of storage.
