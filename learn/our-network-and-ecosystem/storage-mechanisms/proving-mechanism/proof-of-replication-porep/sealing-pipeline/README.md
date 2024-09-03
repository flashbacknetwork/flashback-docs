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
