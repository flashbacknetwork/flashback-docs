# Differences with Flashback

Filecoin brought many cryptographic proofs and a giant leap in the decentralization of data storage. Nonetheless, Filecoin made certain choices that forced the network to store archival data but were ignored for "hot" data storage. You will understand the list of differences between Flashback and Filecoin.

## Virtual Machine

<mark style="color:yellow;">**Filecoin**</mark>: The network's virtual machine, Filecoin Virtual Machine (FVM), is based on WebAssembly (WASM). This gives flexibility in programming language but adds smart contract complexity for deployment. Then, they created the FEVM to support solidity-based deployment, but it has difficulties and stability issues. Finally, while Filecoin worked on this for years, the network currently needs to support Layer-2 capabilities.

<mark style="color:yellow;">**Flashback**</mark>: Compared to Flecoin, Flashback natively supports Layer-2 capabilities by default. Even though the network supports only Solidity, it can benefit from all the improvements in the Ethereum ecosystem. The gas fees are also better managed. Flashback can benefit from improvements like the Dencun upgrade with the data availability layer. This last integration took 1 month after the release of Dencun on the Ethereum network. Finally, Flashback does not need to maintain a custom and complex gas fee system like Filecoin; it is directly related to Ethereum, which is well-known and improved yearly.

## Storage Providers

<mark style="color:yellow;">**Filecoin**</mark>: The network uses the storage providers as miners and must fulfill the [storage power consensus](https://spec.filecoin.io/systems/filecoin\_blockchain/storage\_power\_consensus/) to mine the blocks and validate the network's transactions. This is a time-consuming process for storage providers, and it could be more effective regarding blockchain scalability and carbon footprints. Finally, the security of the blockchain is more fragile depending on the storage capacities, forcing the storage providers to operate for the block rewards rather than the utility of the token itself.

<mark style="color:yellow;">**Flashback**</mark>: Before being a storage provider, you must be a validator and contribute to the staking protocol. Ethereum's staking protocol is highly performant and efficient in terms of security and decentralization. Ethereum is working every day on scalability issues, and Flashback will benefit from them natively. Additionally, the staking protocol is incredibly green, which will reduce Flashback's carbon footprint by 90% compared to Filecoin and other competitors. Once you participate in the staking, you can freely participate as storage providers by enabling the storage proving. It allows a network to focus and grow as utility contributors and separate the blockchain security from the blockchain utility.

## File storage contracts (deals)

<mark style="color:yellow;">**Filecoin**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. The storage fees are vested in the storage providers during the storage duties. This is independent of the quality of the duties, and there is no direct incentive from the clients to incentivize the best-performing providers.

<mark style="color:yellow;">**Flashback**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. Compared to Filecoin, the file storage contracts reward the best-performing storage provider among all the storage providers in the contract. This is supported by the [QoN smart contract](../../quality-of-network-qon-optimizer.md) associated with a deal. Consequently, the Client truly rewards the quality of storage services as they would in a real business or application.

## Storage of proofs

<mark style="color:yellow;">**Filecoin**</mark>: Filecoin designed the first truly decentralized proving system for data storage. This is undoubtedly a great leap for the decentralized ecosystem of public blockchain. This somehow led to the conception of blockchain, resulting in different problems. The first problem was the storage of proofs. It led to extremely high fees filling the whole block while increasing blockchain storage daily. The project developed Filecoin Plus (FIL+): An off-chain system of trusted data storage providers to support more useful data storage. This centralized notary system helped Filecoin grow and reduce the exponential growth of blockchain storage at the cost of security, privacy, and decentralization.

<mark style="color:yellow;">**Flashback**</mark>: The design of the blockchain is fundamental to achieving significant security and decentralization while offering vectors of scalability. Flashback is integrated with the Dencun upgrade and can use the [Blobs](../ethereum-stack-in-nephele/advanced/blockchain-data-availability.md). As explained later in the [QoN optimizer](../../quality-of-network-qon-optimizer.md), the solution streams the proofs to be stored in the Blobs, considerably reducing the [gas fees](https://unchainedcrypto.com/how-much-will-the-dencun-upgrade-really-reduce-ethereum-layer-2-fees-by/) and the blockchain storage growth. Finally, the Layer-2 capabilities will allow developers and companies to extend the storage scalabilities while opening the gate to computing, AI, and other computation-related applications into a unique ecosystem.

## Block rewards

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers receive rewards from the block verifications related to the [storage power consensus](https://spec.filecoin.io/systems/filecoin\_blockchain/storage\_power\_consensus/). This means every sector provides a "power" to mine a new block. The system tends to reward the storage providers with the most significant number of sectors, leading to a network based on capacity rather than the quality of storage performance. While the storage providers receive 25% of block rewards, 75% is unlocked for 180 days. This induces complex risk management for storage providers, and they must integrate this into their business model.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers are staking validators. Due to their staking duties, they receive rewards from the blocks with the Proof-of-Stake (PoS) protocol. The storage is then strictly independent of the block verifications, forcing it to depend on its utility vector. This gives more flexibility, and the storage providers can adjust their resources quickly according to market conditions and needs.

## Deal winning systems

<mark style="color:yellow;">**Filecoin**</mark>: In the Filecoin network, users (individuals or service providers) commit to file storage contracts with storage providers, which allows them to store their data and as sector availability. Winning a deal is independent of any quality or space function.&#x20;

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have deal parameters similar to Filecoin in file storage contracts. (See [on-chain marketplace](on-chain-marketplace.md)) However, the storage providers will win rewards for the [Quality-of-Network (QoN) optimizer](../../quality-of-network-qon-optimizer.md). This forces the network to become increasingly efficient in terms of hardware and setups for the network's users.&#x20;

## Collaterals of storage providers

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers have three distinct collaterals: the initial pledge, the block reward, and the deals. These collaterals guarantee the security and stability of the network's storage. Multiple collaterals can complicate the business model of storage providers, who must integrate all the different collaterals and the associated penalties.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have only one collateral from Ethereum's proof-of-stake (PoS) protocol. All penalties target this collateral. There are no pledges, block rewards, or deal collaterals. This approach eases the business of storage providers while understanding that it will only affect their staking operations but does not directly affect their storage duties.&#x20;

## Penalties

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers can be slashed for the storage duties and the block consensus commitments. The consensus is based on the number of sectors and the commitment of proofs. The different collaterals play a balanced role but can become difficult for the storage provider to manage and track.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers can receive penalties for storage duties and block consensus commitments like Filecoin. The penalties related to block consensus commitments are not related to storage power but to staking operations. Additionally, the protocol applies all the penalties to the staking collateral.&#x20;

## File transfer protocol (FTP)

<mark style="color:yellow;">**Filecoin**</mark>: The network has been designed to support the [InterPlanetary File System (IPFS)](https://ipfs.tech/), which does not support hot storage use cases like AI, cloud gaming, or metaverse.&#x20;

<mark style="color:yellow;">**Flashback**</mark>: The network is considered FTP agnostic, which means IPFS, FTP, HTTPS, and other protocols can operate between the storage providers and the network's clients.&#x20;

