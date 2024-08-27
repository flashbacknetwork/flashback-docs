# Sector Proving: Pipelines and Proofs

Flashback integrates zero-knowledge storage-proving cryptographic mechanisms to guarantee storage security and retrievability from the network's nodes. What does Flashback inherit from Filecoin?\
\
In the Filecoin network, storage proofing is a critical mechanism designed to ensure that storage providers (miners) reliably store the data they are obligated to keep safe under storage deals. This process is fundamental to maintaining the network's integrity and trustworthiness. Filecoin employs two primary types of proofs: **Proof of Replication (PoRep)** and **Proof of Spacetime (PoSt)**.

## Proof of Replication (PoRep)

Proof of Replication is a mechanism by which a storage provider proves to the network that data has been replicated to its unique copy. PoRep happens when the data is first sealed and stored. The process involves the storage provider generating a unique encoding of the data, proving that the data is stored and ensuring its retrievability. This proof ensures that the miner can only claim to store multiple copies of the data after actually doing so.

## Proof of Spacetime (PoSt)

Proof of Spacetime is where **WindowPoSt** comes into play. PoSt is a periodic proof made by storage providers to prove that they continue to store their client's data over time.

### **Window Proof of Spacetime (WindowPoSt)**

WindowPoSt is the mechanism by which storage providers continually prove that they are storing the data they have committed to store. It involves the following:

* **Frequency**: WindowPoSt needs to be submitted at regular intervals for each sector proving that the data is still being stored. This happens according to a schedule that divides the entire set of a miner’s sectors into " partitions " subsets and allocates specific windows during which these proofs must be submitted.
* **Process**: During their respective windows, miners must submit proof for each sector in their partition. This involves scanning the encoded data in each sector and using it to generate a proof. If a miner fails to submit a WindowPoSt in time, or if the proof fails to validate, it can result in penalties, and the sector may be marked as faulty.
* **Faults and Penalties**: If a storage provider fails to provide a valid WindowPoSt for any sector, they are subject to fault fees, and the sector is declared faulty. Faults can be declared temporary (if expected to recover) or permanent (if data is lost). Continued failure to prove storage for a sector can lead to more severe penalties, including sector termination and loss of the stake.

## Importance of Sector Proving

These proofs are vital for several reasons:

* **Network Security**: They prevent dishonest behavior by miners, ensuring miners cannot claim rewards for storage they are not providing.
* **Data Integrity and Availability**: Regularly submitting proofs guarantees that data remains available and retrievable throughout the storage contract.
* **Economic Incentives**: By aligning incentives (via block rewards and penalties), Filecoin ensures that storing data reliably benefits storage providers.
