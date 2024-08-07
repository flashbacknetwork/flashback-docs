# PreCommit 2 (PC2)

After the completion of the PreCommit 1 (PC1) phase, where a sector is encrypted and prepared, the data (along with its scratch space) is transferred to the PreCommit 2 (PC2) task. This transfer marks a critical point in the sealing pipeline.

## **Key Points about PC1 to PC2 Transition:**

* **Server Transition**: Typically, PC2 is executed on a different server than PC1. This is due to the differing computational demands of each phase—PC1 is more CPU-intensive, whereas PC2 relies heavily on GPU capabilities.
* **Data Validation**: In PC2, the previously created encrypted data undergoes validation using the Poseidon hashing algorithm. This algorithm works over the Merkle Tree Directed Acyclic Graph (DAG) that was generated in PC1, ensuring the integrity and correctness of the encryption.

## Hardware and Performance Considerations for PC2

PC2 is particularly demanding on the graphical processing unit (GPU):

* **GPU Requirements**: The task requires a robust GPU with at least 10 GiB of VRAM and over 3500 CUDA cores or equivalent shading units for optimal performance.
* **Execution Time**: On a sufficiently capable GPU, the PC2 phase usually completes within 10 to 20 minutes, significantly faster than the PC1 phase.

## Software Configuration

For best performance, it is recommended to compile the Lotus client with CUDA support, rather than OpenCL, to better leverage NVIDIA GPU architectures.

### Handling Snap Deals

In scenarios involving Snap Deals (where an existing committed capacity sector is retrofitted with new data):

* **Replica Updates**: Instead of re-running the entire PC1 process, a modified procedure updates the replica and proves the update, allowing the sector to be reused efficiently. This process can be executed on the PC2 server or another dedicated worker depending on system configuration and load.

### Chain Commitment and Configuration

Once PC2 is complete:

* **On-Chain Commitment**: A precommit message is prepared for the blockchain. Lotus batches these messages to optimize network and on-chain resource usage if message batching is enabled.
* **Timeout Settings**: There is a default 24-hour timeout after which the precommit message is automatically sent to the blockchain, configurable in the Lotus miner configuration file (`config.toml`).

**Command to Force Pre-Commit Message**: For testing or urgent commitments, you can manually push the precommit message to the blockchain:

```bash
bashCopier le codelotus-miner sectors batching precommit --publish-now
```

**Storage of Sealed Data**: The sealed sector, along with all its cryptographic layers, remains on the scratch volume until the Commit 2 (C2) phase is complete, ensuring data integrity and availability for final blockchain commitment.

This detailed breakdown clarifies each step's purpose and requirements from transitioning between PC1 and PC2, hardware requirements, handling special types of deals, and the commitment process to the blockchain. Understanding these details helps in optimizing the setup and operation of a Filecoin storage system, ensuring efficient and secure data handling throughout the sealing pipeline.
