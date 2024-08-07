# Storage Proving

Filecoin is the first Layer-1 blockchain solution that provides an end-to-end decentralized consensus for verifying the data storage of files in the network's storage providers. &#x20;

Storage proving is a critical mechanism designed to ensure that storage providers (miners) reliably store the data they must keep safe under storage deals. This process is fundamental to maintaining the network's integrity and trustworthiness. Filecoin employs two primary types of proofs: **Proof of Replication (PoRep)** and **Proof of Spacetime (PoSt)**.

## Proof of Replication (PoRep)

Proof of Replication is a mechanism by which a storage provider proves to the network that data has been replicated to its unique copy. <mark style="color:orange;">**PoRep happens when the data is first sealed and stored**</mark><mark style="color:orange;">.</mark> The process involves the storage provider generating a unique data encoding, proving it is stored, and ensuring its retrievability. This proof ensures that the miner can only claim to store multiple copies of the data after actually doing so.

### The Replication Proving Process

The sealing procedure in the Filecoin protocol is a critical process that involves preparing data for storage while ensuring its security and retrievability. This procedure is a part of the Proof of Replication (PoRep) process that storage providers must complete before committing to storing data on the network. Here’s a detailed breakdown of the sealing process:

#### **Pre-Processing of Data**

Data that comes into the Filecoin network is pre-processed before the sealing process begins. This involves dividing the data into manageable pieces that the network can handle. These pieces are then serialized into a format suitable for the sealing process.

#### **Introduction to Sealing**

The sealing process is a multi-step procedure that involves several cryptographic operations:

* **Replication**: The data is replicated to ensure redundancy. This replication isn’t just creating multiple copies; it involves encoding the data cryptographically to generate unique replicas that can be proven independent copies.
* **Encoding**: The replicated data is then encoded using a unique key specific to each copy. This encoding helps ensure the data's confidentiality and adds an additional layer of security.
* **Partitioning**: The encoded data is partitioned into sectors. A sector in Filecoin is the fundamental unit of storage that miners commit to the network. Each sector has a standard size (e.g., 32GiB or 64GiB).
* **Labeling**: Each sector is labeled with a unique identifier that includes information about its contents and its position in the overall data structure. This labeling is crucial for the retrieval and verification processes.

#### **Generation of the Proof**

Once the data is sealed into sectors, the storage provider generates a Proof of Replication. This proof serves as a cryptographic guarantee that the data has been replicated and encoded as described:

* **Creating the Proof**: The proof is created by taking a snapshot of the encoded and partitioned data. This snapshot includes cryptographic hashes of the data segments, which are then compiled into a merkle tree.
* **Submitting the Proof**: The generated proof is then submitted to the blockchain. This submission is a critical step as it registers the proof with the network, making the storage deal official.

#### **Commitment to the Blockchain**

After the proof is successfully generated and submitted, the corresponding sector is committed to the blockchain. This commitment involves recording the details of the sector, including its proof, size, and expected duration of storage, into the Filecoin blockchain.

#### **Continuous Verification**

The sealing process does not end with the submission of the proof. To maintain the integrity of the data, Filecoin requires continuous verification through the Proof of Spacetime (PoSt). This ongoing proof ensures that the data remains intact and accessible over the duration for which it is stored.

### Sealing Pipeline

The sealing pipeline in Filecoin is a sophisticated and multi-stage process essential for storage providers to securely encrypt and commit data to the network. It ensures that data is not only stored securely but is verifiable through cryptographic proofs that confirm the data's continued existence and integrity over time. Below, I provide a detailed breakdown of each step inv, multi-stage process essential for storage providers to securely encrypt and commit data to the network. It ensures that data is not only stored securely but is alsoolved in the sealing pipeline, enhancing clarity and understanding for those new to Filecoin's network operations.

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
   * **Operation**: The system waits for a specified number of blockchain epochs before proceeding to the next step, ensuring no premature commitments.
5. **Commit 1 (C1) and Commit 2 (C2):**
   * **Purpose**: These final steps involve creating a zk-SNARK proof that the data has been replicated and stored correctly.
   * **Operation**: C1 prepares the necessary data for the zk-SNARK proof, which is then generated in C2.
   * **Hardware Requirements**: C2 is GPU-intensive, requiring powerful GPUs to generate the zk-SNARK proof efficiently.

#### Performance Considerations and Tuning

Each phase of the sealing pipeline requires careful management of system resources. Overloading the pipeline by initiating too many processes simultaneously can lead to inefficiencies and increased time for sealing sectors. It is critical for storage providers to understand their system's capabilities and align them with the pipeline's demands to optimize throughput and maintain a steady sealing rate.

To manage resources effectively, it is advisable to:

* Limit concurrent operations in resource-intensive phases like AP and PC1.
* Use enterprise-grade NVMe drives to reduce latency in data transfer and processing.
* Optimize CPU and GPU utilization according to the specific requirements of each phase.

#### Practical Recommendations

* **Hardware Setup**: Equip your system with high-performance CPUs for PC1 and powerful GPUs for PC2 and C2 to handle the cryptographic computations efficiently.
* **System Configuration**: Use the `taskset` command to assign specific cores to different tasks, preventing resource contention and optimizing performance.

## Proof of Spacetime (PoSt)

Proof of Spacetime is where **WindowPoSt** comes into play. PoSt is a periodic proof made by storage providers to prove that they continue to store their client's data over time.

**Window Proof of Spacetime (WindowPoSt)**

WindowPoSt is the mechanism by which storage providers continually prove that they are storing the data they have committed to storing. It involves the following:

* **Frequency**: WindowPoSt must be submitted regularly for each sector, proving that the data is still being stored. This happens according to a schedule that divides the entire set of a miner’s sectors into " partitions " subsets and allocates specific windows during which these proofs must be submitted.
* **Process**: During their respective windows, miners must submit a proof for each sector in their partition. This involves scanning the encoded data in each sector and using it to generate a proof. If a miner fails to submit a WindowPoSt in time, or if the proof fails to validate, it can result in penalties, and the sector may be marked as faulty.
* **Faults and Penalties**: If a storage provider fails to provide a valid WindowPoSt for any sector, they are subject to fault fees, and the sector is declared faulty. Faults can be declared as temporary (if expected to recover) or permanent (if data is lost). Continued failure to prove storage for a sector can lead to more severe penalties, including sector termination and loss of the stake.

#### Importance of Storage Proving

These proofs are vital for several reasons:

* **Network Security**: They prevent dishonest behavior by miners, ensuring miners cannot claim rewards for storage they are not actually providing.
* **Data Integrity and Availability**: Regularly submitting proofs guarantees that data remains available and retrievable over the course of the storage contract.
* **Economic Incentives**: By aligning incentives (via block rewards and penalties), Filecoin ensures that storing data reliably is beneficial for storage providers.
