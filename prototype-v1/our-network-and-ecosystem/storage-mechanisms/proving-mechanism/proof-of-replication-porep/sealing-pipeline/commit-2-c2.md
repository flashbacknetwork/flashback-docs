# Commit 2 (C2)

Commit 2 (C2) is the final and one of the most crucial phases in the Filecoin sealing pipeline. During this phase, the data prepared in Commit 1 (C1) is processed to generate a zk-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge) proof. This proof is then submitted to the Filecoin blockchain, serving as cryptographic evidence that the data has been stored correctly and securely. The accuracy and efficiency of C2 are vital for ensuring that storage providers can prove their storage commitments without issues, thereby earning their storage rewards and maintaining their reputation in the network.

## **Proof Generation**

* **zk-SNARK Proof**: The primary function of C2 is to create a zk-SNARK proof, which compresses the cryptographic data prepared during C1 into a compact proof. This proof can be quickly verified by the blockchain, ensuring that the storage provider has correctly stored the data.
* **Security and Integrity**: The proof generated in C2 must convincingly demonstrate that the data stored in the sector matches the cryptographic commitments made during the earlier stages of the sealing pipeline. This ensures that the storage provider cannot falsely claim to have stored data or tamper with the stored data.

## **Hardware and Performance Considerations**

* **GPU Utilization**: C2 is heavily GPU-bound, meaning it relies on the processing power of a Graphics Processing Unit (GPU) to handle the intensive cryptographic computations required to generate the zk-SNARK proof. High-performance GPUs are essential for efficiently completing this task.
* **CPU and RAM Usage**: While the GPU handles most of the heavy lifting in C2, a powerful CPU is still necessary to manage the data flow and coordinate the operations. RAM requirements are moderate but must be sufficient to support the data structures involved in proof generation.
* **Storage and Scratch Space**: The storage requirements in C2 are mainly concerned with managing the intermediate data produced during proof generation. Fast and reliable SSDs are essential to ensure quick access to this data, minimizing bottlenecks.
* **Duration**: The time required for C2 depends on the performance of the GPU and the size of the sector being processed. Typically, C2 is shorter in duration than earlier phases like PreCommit 1, but it still requires significant computational resources to complete efficiently.

## **Process Execution**

* **Proof Compression**: The data from C1 is processed through complex cryptographic algorithms to produce a zk-SNARK proof. This involves compressing the data into a form that can be easily verified by the blockchain while retaining all necessary cryptographic guarantees.
* **Optimization Strategies**: Utilizing GPUs with high CUDA cores or shading units is recommended to optimize the proof generation process. Additionally, ensuring that the system's storage and memory subsystems are fast and responsive can further reduce the time required for C2.

## **Final Steps**

* **Proof Submission**: After the zk-SNARK proof is generated, it is submitted to the Filecoin blockchain. This submission finalizes the sealing process for the sector, allowing the storage provider to earn their storage rewards and demonstrate their commitment to the network.
* **Batched Submissions**: To optimize network fees and reduce congestion, multiple C2 proofs can be batched together into a single transaction. This approach is particularly useful when sealing multiple sectors simultaneously.

The Commit 2 (C2) phase is the culmination of the Filecoin sealing process, where all the preparation and computations come together to produce a final proof of storage. By ensuring that C2 is executed efficiently and accurately, storage providers can maximize their performance, minimize costs, and maintain a strong presence in the Filecoin network. Proper hardware configuration, particularly with regard to GPU capabilities, is essential for optimizing this phase and ensuring successful proof generation.
