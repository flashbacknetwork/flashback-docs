# Differences with Flashback

Filecoin brought many cryptographic proofs and a giant leap in the decentralization of data storage. Nonetheless, Filecoin made certain choices that forced the network to store archival data but were ignored for "hot" data storage. You will understand the list of differences between Flashback and Filecoin.

## Virtual Machine

<mark style="color:yellow;">**Filecoin**</mark>: The network has its own virtual machine, Filecoin Virtual Machine (FVM), based on WebAssembly (WASM). This gives flexibility in programming language but adds smart contract complexity for deployment. Then, they created the FEVM to support solidity-based deployment, but it has difficulties in using it and stability issues. Finally, the network does not support Layer-2 capabilities for now.

<mark style="color:yellow;">**Flashback**</mark>: Compared to Flecoin, Flashback natively supports Layer-2 capabilities by default. Even though the network supports only solidity, it can benefit from all the improvements in the Ethereum ecosystem. Additionally, the gas fees are better managed, and Flashback can benefit from improvements like the Dencun upgrade with data availability layer.

## File storage contracts (deals)

<mark style="color:yellow;">**Filecoin**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. The storage fees are vested in the storage providers during the storage duties. This is independent of the quality of the duties, and there is no direct incentive from the clients to incentivize the best-performing providers.

<mark style="color:yellow;">**Flashback**</mark>: The network user can deploy deals with storage providers. They decide on the storage providers, the duration, and the storage allocation according to the files' size. Compared to Filecoin, the file storage contracts reward the best-performing storage provider among all the storage providers in the contract. This is supported by the QoN smart contract associated with a deal. The consequence is that the Client truly rewards the quality of storage services as they would in a real business or application.

## Storage of proofs

<mark style="color:yellow;">**Filecoin**</mark>: FIL+

<mark style="color:yellow;">**Flashback**</mark>: Dencun

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

