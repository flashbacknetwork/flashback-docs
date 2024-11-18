# 🌗 Differences with Filecoin

Filecoin brought many cryptographic proofs and a giant leap in the decentralization of data storage. Nonetheless, this solution made certain choices that forced the network to store archival data but were ignored for "hot" data storage.&#x20;

## Virtual Machine

<mark style="color:yellow;">**Filecoin**</mark>: The network's virtual machine, Filecoin Virtual Machine (FVM), is based on WebAssembly (WASM). This gives flexibility in programming language but adds smart contract complexity for deployment. Then, they created the FEVM to support solidity-based deployment, but it has difficulties and stability issues. Finally, while Filecoin worked on this for years, the network currently needs to support Layer-2 capabilities.

<mark style="color:yellow;">**Flashback**</mark>: Compared to Flecoin, Flashback natively supports Layer-2 capabilities by default. Even though the network supports only Solidity, it can benefit from all the improvements in the Ethereum ecosystem. The gas fees are also better managed. Flashback can benefit from improvements like the Dencun upgrade with the data availability layer. This last integration took 1 month after the release of Dencun on the Ethereum network. Finally, Flashback does not need to maintain a custom and complex gas fee system like Filecoin; it is directly related to Ethereum, which is well-known and improved yearly.

## Storage Providers

<mark style="color:yellow;">**Filecoin**</mark>: The network uses **the storage providers as miners** and must fulfill the [storage power consensus](https://spec.filecoin.io/systems/filecoin\_blockchain/storage\_power\_consensus/) to mine the blocks and validate the network's transactions. This is a time-consuming process for storage providers, and it could be more effective regarding blockchain scalability and carbon footprints. Finally, the security of the blockchain is more fragile depending on the storage capacities, forcing the storage providers to operate for the block rewards rather than the utility of the token itself.

<mark style="color:yellow;">**Flashback**</mark>: Before being a storage provider, you must be a validator and contribute to the staking protocol. Ethereum's staking protocol is highly performant and efficient regarding security and decentralization. Ethereum is working daily on scalability issues, and Flashback will benefit from them natively. Additionally, the staking protocol is incredibly green, which will reduce Flashback's carbon footprint by 90% compared to Filecoin and other competitors. Once you participate in the staking, you can freely participate as storage providers by enabling the storage proving. It allows a network to focus and grow as utility contributors and separate the blockchain security from the blockchain utility.

## **Change in Sector Proving**

<mark style="color:yellow;">**Filecoin:**</mark> Storage providers are miners and integral to the network's security and consensus. They must fulfill the storage power consensus, which ties the ability to mine blocks and validate transactions to the amount of storage they provide to the network. This process, known as Proof-of-Replication (PoRep) followed by Proof-of-Spacetime (PoSt), is time-consuming and requires significant computational and storage resources. Miners must continuously prove they are storing data, directly impacting their ability to earn block rewards. While effective for ensuring data storage, this mechanism links blockchain security too closely with storage capacity, which can limit scalability and increase the carbon footprint due to the heavy resource demands. Additionally, the focus on storage capacity for securing the blockchain may detract from the overall utility of the network and force providers to operate primarily for block rewards.

<mark style="color:yellow;">**Flashback:**</mark> The roles of storage providers and blockchain validators are distinct. Before becoming a storage provider, participants must act as validators by contributing to the staking protocol, similar to Ethereum’s Proof-of-Stake (PoS) system. This PoS protocol is highly efficient and secure, offering robust decentralization and scalability while significantly reducing carbon emissions. Once participants have staked, they can opt to become storage providers, focusing solely on storage duties without needing block validation. This separation of roles allows Flashback to grow its network based on utility contributions, as storage providers are not burdened with blockchain security tasks. Consequently, Flashback does not require the WinningPoSt mechanism, as block validation is handled exclusively through PoS. This approach leads to a more scalable, environmentally friendly network where blockchain security is decoupled from storage capacity.

## File storage contracts (deals)

<mark style="color:yellow;">**Filecoin**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. The storage fees are vested in the storage providers during the storage duties. This is independent of the quality of the duties, and there is no direct incentive from the clients to incentivize the best-performing providers.

<mark style="color:yellow;">**Flashback**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. Compared to Filecoin, the file storage contracts reward the best-performing storage provider among all the storage providers in the contract. This is supported by the [QoN smart contract](quality-of-network-qon-optimizer.md) associated with a deal. Consequently, the Client truly rewards the quality of storage services as they would in a real business or application.

## Storage of proofs

<mark style="color:yellow;">**Filecoin**</mark>: Filecoin designed the first truly decentralized proving system for data storage. This is undoubtedly a great leap for the decentralized ecosystem of public blockchain. This somehow led to the conception of blockchain, resulting in different problems. The first problem was the storage of proofs. It led to extremely high fees filling the block while increasing daily blockchain storage. The project developed Filecoin Plus (FIL+): An off-chain system of trusted data storage providers to support more useful data storage. This centralized notary system helped Filecoin grow and reduce the exponential growth of blockchain storage at the cost of security, privacy, and decentralization.

<mark style="color:yellow;">**Flashback**</mark>: The design of the blockchain is fundamental to achieving significant security and decentralization while offering vectors of scalability. Flashback is integrated with the Dencun upgrade and can use the [Blobs](ethereum-stack-in-nephele/advanced/blockchain-data-availability.md). As explained later in the [QoN optimizer](quality-of-network-qon-optimizer.md), the solution streams the proofs to be stored in the Blobs, considerably reducing the [gas fees](https://unchainedcrypto.com/how-much-will-the-dencun-upgrade-really-reduce-ethereum-layer-2-fees-by/) and the blockchain storage growth. Finally, the Layer-2 capabilities will allow developers and companies to extend the storage scalabilities while opening the gate to computing, AI, and other computation-related applications into a unique ecosystem.

## Block rewards and validation Consensus

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers receive rewards from the block verifications related to the [expected consensus](storage-mechanisms/expected-consensus.md). This means every sector provides a "power" to mine a new block. The system tends to reward the storage providers with the most significant number of sectors, leading to a network based on capacity rather than the quality of storage performance. While the storage providers receive 25% of block rewards, 75% is unlocked for 180 days. This induces complex risk management for storage providers, and they must integrate this into their business model.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers are staking validators. Due to their staking duties, they receive rewards from the blocks with the Proof-of-Stake (PoS) protocol. The storage is then strictly independent of the block verifications, forcing it to depend on its utility vector. This gives more flexibility, and the storage providers can adjust their resources quickly according to market conditions and needs. As a consequence, the WinningPoSt is unnecessary in our network.

## Deal winning systems

<mark style="color:yellow;">**Filecoin**</mark>: In the Filecoin network, users (individuals or service providers) commit to file storage contracts with storage providers, which allows them to store their data and as sector availability. Winning a deal is independent of any quality or space function.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have deal parameters similar to Filecoin in file storage contracts. (See [on-chain marketplace](storage-mechanisms/on-chain-marketplace/)) However, the storage providers will win rewards for the [Quality-of-Network (QoN) optimizer](quality-of-network-qon-optimizer.md). This forces the network to become increasingly efficient in terms of hardware and setups for the network's users.

## Collaterals of storage providers

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers have three distinct collaterals: the initial pledge, the block reward, and the deals. These collaterals guarantee the security and stability of the network's storage. Multiple collaterals can complicate the business model of storage providers, who must integrate all the different collaterals and the associated penalties.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have only one collateral from Ethereum's proof-of-stake (PoS) protocol. All penalties for block validation target this collateral. There are no pledges or block rewards related to storage. Nonetheless, Flashback keeps the storage deal collateral to pay the QoN contract fees. This approach eases the business of storage providers while understanding that it will only affect their staking operations but does not directly affect their storage duties.

## Penalties

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers can be slashed for the storage duties and the block consensus commitments. The consensus is based on the number of sectors and the commitment of proofs. The different collaterals play a balanced role but can become difficult for the storage provider to manage and track.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers can receive penalties for storage duties and block consensus commitments like Filecoin. The penalties related to block consensus commitments are not related to storage power but to staking operations. Additionally, the protocol applies all the penalties to the staking collateral.

## File transfer protocol (FTP)

<mark style="color:yellow;">**Filecoin**</mark>: The network has been designed to support the [InterPlanetary File System (IPFS)](https://ipfs.tech/), which does not support hot storage use cases like AI, cloud gaming, or metaverse.

<mark style="color:yellow;">**Flashback**</mark>: The network is considered FTP agnostic, which means IPFS, FTP, HTTPS, and other protocols can operate between the storage providers and the network's clients.

## Utility: "cold" vs "hot" storage

<mark style="color:yellow;">**Filecoin**</mark>: The network is supporting the growth of storage providers in terms of capacity and to commit a setup to mine blocks and not the utility itself. Hence, Filecoin aims to be the world's archive system, which is related to ["cold" storage](https://www.seagate.com/fr/fr/blog/what-is-cold-data-storage/).

<mark style="color:yellow;">**Flashback**</mark>: The network promotes and rewards the storage providers with the best data storage performance. This unique incentive mechanism only supports the ["hot" storage](https://www.logicmonitor.com/blog/hot-storage-vs-cold-storage) of AI and other high-demanding data applications and services.
