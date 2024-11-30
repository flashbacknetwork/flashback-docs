# Commit 1 (C1)

Commit 1 (C1) is a critical phase in the Filecoin sealing pipeline, where the groundwork for generating the final proof of storage is laid. This phase is primarily concerned with preparing the necessary data structures and performing initial computations that will eventually be used to create a zk-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge) proof. This proof will attest to the correctness of the data replication process and ensure that the data has been stored as required by the network.

## **Cryptographic Foundations**

* **Preparation for zk-SNARK Proof**: In C1, the initial computations required to generate the zk-SNARK proof in the next phase (Commit 2) are carried out. This involves setting up data structures and performing necessary cryptographic operations to ensure that the proof can be efficiently and correctly generated.
* **Data Integrity**: The operations performed in C1 are crucial for ensuring that the data stored within a sector remains secure and tamper-proof. The proofs generated from this phase will be part of the final proof that is submitted to the blockchain, proving the storage provider's commitment to the network.

## **Hardware and Performance Considerations**

* **CPU Utilization**: The C1 phase is CPU-bound, meaning that it primarily relies on the processing power of the CPU to execute the necessary computations. While it is less demanding than the PC1 phase, it still requires a robust CPU to perform the operations efficiently.
* **Memory and Storage Requirements**: The memory usage during C1 is relatively moderate compared to the initial sealing phases, but it still requires sufficient RAM to prepare data structures. The storage requirements involve managing intermediate data that will be used in the final proof generation.
* **Duration**: The C1 phase is typically brief, often taking only a few seconds to a few minutes, depending on the hardware configuration and the size of the sector being processed.

## **Process Execution**

* **Data Structure Initialization**: The primary task of C1 is to initialize and prepare the data structures that will be used in generating the zk-SNARK proof. This involves organizing the encoded data from previous phases and ensuring it is ready for the final proof generation.
* **Optimizations**: While C1 is less resource-intensive than earlier phases like PC1, optimizing the CPU and memory usage during this phase can still contribute to overall efficiency in the sealing pipeline. Proper management of resources during C1 ensures that the transition to C2, where the final proof is generated, is smooth and efficient.

## **Final Steps**

* **Transition to Commit 2 (C2)**: Once the C1 phase is complete, the system is ready to proceed to C2, where the final zk-SNARK proof will be generated. The outputs from C1 are crucial for ensuring that the proof generation in C2 is both accurate and efficient.

Understanding the role of the Commit 1 (C1) phase in the Filecoin sealing pipeline is essential for optimizing the sealing process and ensuring the integrity and security of stored data. By properly managing the hardware resources and optimizing the execution of C1, storage providers can enhance their overall performance and contribute to the robustness of the Filecoin network.
