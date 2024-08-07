# Commit 1 (C1) and Commit 2 (C2)

The Commit 1 (C1) and Commit 2 (C2) phases in the Filecoin sealing pipeline are critical steps that finalize the storage process, securing data and ensuring its verifiability on the blockchain. Below, I'll detail these phases to enhance understanding:

## Commit 1 (C1)

* **Purpose**: The C1 phase acts as an intermediate step where preparations are made to generate a cryptographic proof. This proof verifies that data has been sealed according to the Filecoin protocol's standards.
* **Process**: This phase is heavily reliant on CPU resources as it involves assembling and processing data needed for the zk-SNARK proof generated in the subsequent C2 phase.
* **Duration**: Typically, C1 completes very quickly, often within seconds, reflecting its role as a preparatory step rather than a heavy computational process.
* **Execution Recommendation**: It is advisable for storage providers to run C1 on the same server as C2. This co-location minimizes data transfer delays between the two phases and streamlines the overall processing time.

## Commit 2 (C2)

* **Purpose**: C2 is the final step in the sealing pipeline where the zk-SNARK proof is created. This proof is critical as it provides the cryptographic guarantee required by the Filecoin network to verify the integrity and authenticity of the sealed data.
* **Process**: C2 is GPU-intensive, utilizing substantial graphical processing power to compute the zk-SNARK. This step consolidates all previous data transformations into a final proof that can be verified independently by anyone on the network.
* **Hardware Requirements**: Due to its GPU-bound nature, running C2 on a high-performance GPU setup is crucial. This ensures the proof is generated efficiently and within the required time constraints.

## On-Chain Commitment

* **Commit Message Posting**: After C2 completes, a commit message that includes the zk-SNARK proof is prepared for posting to the Filecoin blockchain. This message is critical as it serves as the on-chain record of the data being securely stored.
* **Batching Process**: To optimize network and resource usage, commit messages are typically batched and held for up to 24 hours before being sent to the blockchain. This batching helps in managing the blockchain's load and reduces the frequency of messages.
* **Immediate Commit Option**: For scenarios requiring immediate on-chain commitment, such as testing or urgent updates, storage providers can use the command `lotus-miner sectors batching commit --publish-now` to bypass the batching process and push commit messages directly.

## Storage and Retrieval

* **Long-Term Storage**: Once sealed and verified, the sector is stored in the miner's long-term storage. This setup is essential for ensuring that data remains accessible for future retrieval requests, complying with the network's durability requirements.
* **Retrieval Readiness**: Along with the sealed sectors, miners often store unsealed copies of the data. These are necessary for quick retrieval operations, as unsealing data can be time-consuming and computationally expensive.

Understanding these phases in detail helps storage providers optimize their operations and maintain compliance with Filecoin's stringent security and verifiability standards.
