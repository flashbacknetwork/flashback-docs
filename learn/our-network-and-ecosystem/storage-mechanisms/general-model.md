# The Model

**The storage model of Nephele was designed using Filecoin but has many differences. You will find a section at the end of the page if a difference exists.**

## **Filecoin's Model**

Filecoin's model is designed to facilitate decentralized storage solutions on a blockchain network, focusing on security, reliability, and efficiency. Here’s a detailed look into how Filecoin manages its storage:

<mark style="color:yellow;">**1. Storage Providers and Sectors:**</mark> Filecoin's network consists of storage providers who offer their disk space to clients in exchange for FIL tokens. These providers store data in "sectors," cryptographically sealed units to ensure their contents cannot be altered once written​.

<mark style="color:yellow;">**2. Deals and Data Storage:**</mark> Clients initiate storage by creating deals with storage providers. These deals specify the terms for storing data, such as duration and price. Once agreed upon, data is transferred to the storage provider and packaged into sectors. The provider then seals these sectors and commits them to the Filecoin blockchain, providing a publicly verifiable record of the data stored and its integrity​.

<mark style="color:yellow;">**3. Proving Storage:**</mark> To ensure that data is stored correctly and reliably, Filecoin employs a mechanism called Proof-of-Replication (PoRep) for the initial sealing and Proof-of-Spacetime (PoSt) for ongoing verification. PoRep proves that the data has been replicated to its unique copy, while PoSt ensures that it is stored over time. These proofs help maintain the integrity and reliability of the data stored on the network.

<mark style="color:yellow;">**4. Retrieval Market:**</mark> Filecoin also features a retrieval market where clients can efficiently retrieve their stored data from the network. Retrieval miners facilitate this process incentivized to provide clients with the fastest access to their data. The retrieval process does not involve the blockchain directly. Still, it is handled via off-chain transactions, making it efficient and scalable.

<mark style="color:yellow;">**5. Incentives and Penalties:**</mark> Storage providers are compensated with FIL tokens for their services, disbursed as block rewards. They can also earn additional fees by serving data quickly in the retrieval market. Conversely, providers face penalties (or "slashing") if they fail to prove they are still storing the data they committed to or if they lose the data​.

<mark style="color:yellow;">**6. Technological Infrastructure:**</mark> Filecoin storage providers typically utilize advanced file systems like ZFS due to their robustness, data integrity features, and support for high storage capacities. Providers must also manage their hardware effectively, ensuring data redundancy and protection to maintain service quality and reliability​​.

## Differences between Filecoin and Nephele



