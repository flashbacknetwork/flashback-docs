# Sealing Pipeline

The sealing pipeline in Filecoin is a sophisticated and multi-stage process essential for storage providers to securely encrypt and commit data to the network. It ensures that data is not only stored securely but is verifiable through cryptographic proofs that confirm the data's continued existence and integrity over time. Below, I provide a detailed breakdown of each step involved in the sealing pipeline, enhancing clarity and understanding for those new to Filecoin's network operations.

## Overview of the Sealing Pipeline

The sealing process comprises several distinct phases, each with specific hardware requirements and performance considerations:

1. **AddPiece (AP):**
   * **Purpose**: This initial phase involves taking the raw data in CAR-file format and preparing it for the cryptographic processes that follow.
   * **Operation**: Data is written to the sealing scratch space, preparing for the next phase, PreCommit 1.
   * **Hardware Utilization**: Primarily uses CPU resources and requires substantial disk I/O operations. It is recommended to limit the number of concurrent AP operations to manage system load effectively.
2. **PreCommit 1 (PC1):**
   * **Purpose**: This phase is crucial for transforming the raw data into a cryptographically secure format through the Proof-of-Replication (PoRep) process.
   * **Operation**: The data undergoes SDR (Seal Data Replica) encoding, creating multiple layers of data, which enhances security.
   * **Hardware Requirements**: Intensive CPU usage, particularly benefiting from CPUs with SHA256 extensions, which are optimal for cryptographic calculations.
3. **PreCommit 2 (PC2):**
   * **Purpose**: Validates the encoding done by PC1 using the Poseidon hashing algorithm to create a Merkle Tree DAG of the encoded data.
   * **Operation**: Transfers the entire scratch space prepared in PC1 to PC2, shifting from CPU-intensive tasks to GPU-intensive tasks.
   * **Hardware Requirements**: Primarily uses GPUs to handle the computationally intensive task of hashing the data layers.
4. **WaitSeed:**
   * **Purpose**: A built-in waiting period mandated by the blockchain to enhance security measures between the sealing and committing phases.
   * **Operation**: The system waits for several blockchain epochs before proceeding to the next step, ensuring no premature commitments.
5. **Commit 1 (C1) and Commit 2 (C2):**
   * **Purpose**: These final steps involve creating a zk-SNARK proof that the data has been replicated and stored correctly.
   * **Operation**: C1 prepares the necessary data for the zk-SNARK proof, which is then generated in C2.
   * **Hardware Requirements**: C2 is GPU-intensive, requiring powerful GPUs to generate the zk-SNARK proof efficiently.





## PreCommit 1 (PC1)

PreCommit 1 (PC1) is a critical and resource-intensive phase in the Filecoin sealing pipeline. It primarily involves the cryptographic securing of data within a sector and is foundational in preparing the data for long-term storage on the Filecoin network. Let's break down the PC1 process, including a closer look at the 11 layers of data encoding it involves.

### Overview

**Cryptographic Securing**: In PC1, each sector—whether it already contains data or not—is cryptographically transformed using Proof-of-Replication (PoRep). This involves encoding the data in such a way that proves the storage provider (SP) is uniquely storing the client's data.

#### **Parameters and Environment Setup**:

* **Cryptographic Parameters**: The process begins with loading cryptographic parameters from a cache. These parameters are essential for the encoding process and are stored on enterprise-level NVMe storage to minimize latency.
* **CPU Requirements**: PC1 is executed as a single-threaded process that is heavily reliant on CPU capabilities, particularly those that support SHA256 extensions. Optimal CPUs for this task include AMD Epyc Milan/Rome and Intel Xeon Ice Lake processors with 32 cores or more.

#### **Memory and Storage Utilization**:

* The data for each sector is processed to create multiple layers of encoded data. Specifically, PC1 generates 11 layers for each sector.
* **Memory Consumption**: The scratch space required for a 32 GiB sector is approximately 384 GiB, and for a 64 GiB sector, around 768 GiB. This expansive use of scratch space is due to the need to manage multiple encoded versions of the data simultaneously.

#### **Process Execution**:

* To ensure the sealing pipeline operates efficiently without overloading the system, it's crucial to manage the number of concurrent PC1 jobs. This is typically controlled by setting the `PC1_32G_MAX_CONCURRENT` environment variable, which limits the number of simultaneous encoding jobs per server.

### The 11 Layers of Data Encoding

During the PC1 phase, 11 distinct layers of data are created as part of the sector encoding process. Here’s a generalized overview of what these layers represent:

* **Layer Purpose**: Each layer serves as a step in the transformation process, enhancing the data's security and ensuring it is stored non-duplicable.
* **Technical Details**: The layers are generated through a series of hash functions and encoding steps, collectively building a complex and secure representation of the original data. This multi-layered approach not only secures the data but also prepares it for the generation of a unique replication proof.

### **Final Steps and Time Considerations**

* **Sealing Time**: The duration to seal a single 32 GiB sector typically takes about 3 hours, although this can vary based on the server’s hardware specifications and the workload of other tasks being processed simultaneously.

By understanding and optimizing each component of PC1, storage providers can significantly enhance their operational efficiency and ensure compliance with the Filecoin network's security standards. This detailed setup not only helps in managing the computational load but also aligns with Filecoin’s requirements for data integrity and proof of storage.



## PreCommit 2 (PC2)







#### Performance Considerations and Tuning

Each phase of the sealing pipeline requires careful management of system resources. Overloading the pipeline by initiating too many processes simultaneously can lead to inefficiencies and increased time for sealing sectors. It is critical for storage providers to understand their system's capabilities and align them with the pipeline's demands to optimize throughput and maintain a steady sealing rate.

To manage resources effectively, it is advisable to:

* Limit concurrent operations in resource-intensive phases like AP and PC1.
* Use enterprise-grade NVMe drives to reduce latency in data transfer and processing.
* Optimize CPU and GPU utilization according to the specific requirements of each phase.

#### Practical Recommendations

* **Hardware Setup**: Equip your system with high-performance CPUs for PC1 and powerful GPUs for PC2 and C2 to handle the cryptographic computations efficiently.
* **System Configuration**: Use the `taskset` command to assign specific cores to different tasks, preventing resource contention and optimizing performance.
