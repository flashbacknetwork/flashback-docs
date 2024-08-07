# Differences with Flashback

Filecoin brought many cryptographic proofs and a giant leap in the decentralization of data storage. Nonetheless, Filecoin made certain choices that forced the network to store archival data but were ignored for "hot" data storage. You will understand the list of differences between Flashback and Filecoin.

## Block rewards

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers receive rewards from the block verifications related to the [storage power consensus](https://spec.filecoin.io/systems/filecoin\_blockchain/storage\_power\_consensus/). This means every sector provides a "power" to mine a new block. The system tends to reward the storage providers with the most significant number of sectors, leading to a network based on capacity rather than the quality of storage performance. While the storage providers receive 25% of block rewards, 75% is unlocked for 180 days. This induces complex risk management for storage providers, and they must integrate this into their business model.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers are staking validators. Due to their staking duties, they receive rewards from the blocks with the Proof-of-Stake (PoS) protocol. The storage is then strictly independent of the block verifications, forcing it to depend on its utility vector. This gives more flexibility, and the storage providers can adjust their resources quickly according to market conditions and needs.

## Deal winning systems

<mark style="color:yellow;">**Filecoin**</mark>: In the Filecoin network, users (individuals or service providers) commit to file storage contracts with storage providers, which allows them to store their data and as sector availability. Winning a deal is independent of any quality or space function.&#x20;

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have deal parameters similar to Filecoin in file storage contracts. (See [on-chain marketplace](on-chain-marketplace.md)) However, the storage providers will win rewards for the [Quality-of-Network (QoN) optimizer](../../quality-of-network-qon-optimizer.md). This forces the network to become increasingly efficient in terms of hardware and setups for the network's users.&#x20;

## Collaterals of Storage Providers

<mark style="color:yellow;">**Filecoin**</mark>: Storage providers have three distinct collaterals: the initial pledge, the block reward, and the deals. These collaterals guarantee the security and stability of the network's storage. Multiple collaterals can complicate the business model of storage providers, who must integrate all the different collaterals and the associated penalties.

<mark style="color:yellow;">**Flashback**</mark>: Storage providers have only one collateral coming from Ethereum's proof-of-stake (PoS) protocol. All the penalties are then targeting this collateral.

## Penalties

**Filecoin**: Storage providers can be slashed for the storage duties and the block consensus commitments. The consensus is based on the number of sectors and the commitment of proofs. The different collaterals play a balanced role but can become difficult for the storage provider to manage and track.

**Flashback**: Storage providers can receive penalties for the storage duties and the block consensus commitments. The penalties related to block consensus commitments are not related to the storage power but the staking operations. Additionally, the protocol applies all the penalties on the staking collateral.&#x20;

