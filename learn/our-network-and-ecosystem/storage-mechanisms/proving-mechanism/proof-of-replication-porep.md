# Proof of Replication (PoRep)

Proof of Replication (PoRep) is a mechanism by which a storage provider proves to the network that data has been replicated to its unique copy. <mark style="color:orange;">**PoRep happens when the data is first sealed and stored**</mark><mark style="color:orange;">.</mark> The process involves the storage provider generating a unique data encoding, proving it is stored, and ensuring its retrievability. This proof ensures that the storage provider can only claim to store multiple copies of the data after actually doing so.

## **Pre-Processing of Data**

Data in the Filecoin network is pre-processed before the sealing process begins. This involves dividing the data into manageable pieces that the network can handle. These pieces are then serialized into a format suitable for the sealing process.

## **The Sealing**

The sealing process is a multi-step procedure that involves several cryptographic operations:

* **Replication**: The data is replicated to ensure redundancy. This replication isn’t just creating multiple copies; it involves encoding the data cryptographically to generate unique replicas that can be proven independent copies.
* **Encoding**: The replicated data is then encoded using a unique key specific to each copy. This encoding helps ensure the data's confidentiality and adds layer of security.
* **Partitioning**: The encoded data is partitioned into sectors. A sector in Filecoin is the fundamental unit of storage that miners commit to the network. Each sector has a standard size (e.g., 32GiB or 64GiB).
* **Labeling**: Each sector has a unique identifier that includes information about its contents and its position in the overall data structure. This labeling is crucial for the retrieval and verification processes.

## **Generation of the Proof**

Once the data is sealed into sectors, the storage provider generates a Proof of Replication. This proof serves as a cryptographic guarantee that the data has been replicated and encoded as described:

* **Creating the Proof**: The proof is created by taking a snapshot of the encoded and partitioned data. This snapshot includes cryptographic hashes of the data segments, which are then compiled into a merkle tree.
* **Submitting the Proof**: The generated proof is then submitted to the blockchain. This submission is a critical step as it registers the proof with the network, making the storage deal official.

## **Commitment to the Blockchain**

After the proof is successfully generated and submitted, the corresponding sector is committed to the blockchain. This commitment involves recording the details of the sector, including its proof, size, and expected duration of storage, into the Filecoin blockchain.

## **Continuous Verification**

The sealing process does not end with the submission of the proof. To maintain the integrity of the data, Filecoin requires continuous verification through the Proof of Spacetime (PoSt). This ongoing proof ensures that the data remains intact and accessible over the duration for which it is stored.
