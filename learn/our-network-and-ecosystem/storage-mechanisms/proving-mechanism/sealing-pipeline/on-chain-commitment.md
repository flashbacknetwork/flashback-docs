# On-Chain Commitment

## On-Chain Commitment

* **Commit Message Posting**: After C2 completes, a commit message that includes the zk-SNARK proof is prepared for posting to the Filecoin blockchain. This message is critical as it serves as the on-chain record of securely stored data.
* **Batching Process**: To optimize network and resource usage, commit messages are typically batched and held for up to 24 hours before being sent to the blockchain. This batching helps manage the blockchain's load and reduces the frequency of messages.
* **Immediate Commit Option**: For scenarios requiring immediate on-chain commitment, such as testing or urgent updates, storage providers can use the command `lotus-miner sectors batching commit --publish-now` to bypass the batching process and push commit messages directly.

## Storage and Retrieval

* **Long-Term Storage**: Once sealed and verified, the sector is stored in the miner's long-term storage. This setup is essential for ensuring that data remains accessible for future retrieval requests, complying with the network's durability requirements.
* **Retrieval Readiness**: Along with the sealed sectors, miners often store unsealed copies of the data. These are necessary for quick retrieval operations, as unsealing data can be time-consuming and computationally expensive.

Understanding these phases in detail helps storage providers optimize their operations and maintain compliance with Filecoin's stringent security and verifiability standards.
