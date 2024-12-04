# SnapDeal Pipeline

The SnapDeal pipeline in Filecoin is a specialized process designed to handle the update of already committed sealed sectors by inserting deal data into them. This process includes several unique phases that ensure the integrity and security of the updated sectors. Below is an outline of the tasks involved in the SnapDeal pipeline, along with their purpose, operation, and hardware requirements.

## **1.** [**Replica Update**](replica-update.md)

* **Purpose**: The Replica Update task is responsible for encoding new, unsealed deal data into an existing sealed sector. This task ensures that the updated sector remains cryptographically secure, preventing any foreknowledge of the output bytes in the new sealed sector.
* **Operation**: The process encodes the incoming deal data into the sealed sector while maintaining the integrity of the original data. This is achieved through additional logic that ensures the output is unpredictable, enhancing network security.
* **Hardware Requirements**:
  * **CPU**: High CPU usage, similar to the PreCommit 2 task, as it involves complex cryptographic operations.
  * **Storage**: Requires access to the original sealed sector and sufficient scratch space for processing the update.
  * **GPU**: While primarily CPU-intensive, GPUs can be used to accelerate certain cryptographic processes if available.

## **2.** [**Prove Replica Update 1**](prove-replica-update-1.md)

* **Purpose**: This phase is analogous to the Commit 1 task in the standard sealing pipeline but involves slightly lighter proofs. It focuses on proving that the new deal data has been correctly encoded into the existing sealed sector.
* **Operation**: The task generates an initial proof that confirms the successful encoding of the new data. This proof is crucial for validating the integrity of the updated sector before proceeding to the next phase.
* **Hardware Requirements**:
  * **CPU**: High CPU utilization for generating the initial proof, though slightly less intensive than in a full Commit 1 task.
  * **Storage**: Requires storage to manage the intermediate proof data.

## **3.** [**Prove Replica Update 2**](prove-replica-update-2.md)

* **Purpose**: The final phase of the SnapDeal pipeline, Prove Replica Update 2, involves compressing the proof from the previous task into a smaller, zk-SNARK proof. This compact proof is essential for verifying on the blockchain that the new data has been securely encoded into the sealed sector.
* **Operation**: The task compresses the proof using zk-SNARKs, making it small enough for efficient on-chain verification. The resulting proof confirms that the updated sector meets the network's cryptographic standards.
* **Hardware Requirements**:
  * **CPU**: The task can be performed using the CPU, though it is computationally intensive.
  * **GPU**: Utilizing a GPU can significantly speed up the zk-SNARK generation process, making this phase more efficient.
  * **Storage**: Requires adequate storage for managing both the intermediate and final proof data.

The SnapDeal pipeline ensures that updating sealed sectors with new deal data maintains the cryptographic security and integrity required by the Filecoin network. This process is critical for providers wishing to optimize their storage capacity by incorporating new deals into existing sectors without compromisingsecurity.
