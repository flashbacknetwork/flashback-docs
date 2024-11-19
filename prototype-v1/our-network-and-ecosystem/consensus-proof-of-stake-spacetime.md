---
hidden: true
---

# Proof-of-Stake-Spacetime

To achieve distributed consensus, each validator in Flashback must perform different checks on the blockchain. There are manifold distributed consensus mechanisms, such as the Nakamoto or [Slasher ](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm)consensus.

The Flashback network is a blockchain with on-chain and off-chain data storage. We use a hybrid consensus approach known as **Proof-of-Stake-Spacetime (PoS-ST)** to validate both functionalities effectively.

This proposal upgrades the current Gasper's [Proof-of-Stake (PoS)](ethereum-stack-in-nephele/validators/proof-of-stake.md) consensus mechanism by using [Proof-of-Spacetime (PoSt)](storage-mechanisms/proving-mechanism/proof-of-spacetime-post/) functionalities. It aims to enable decentralized file storage on an Ethereum Virtual Machine (EVM)-compatible blockchain. The core addition, termed PoS-ST, extends the validator's staking role to have transaction validation and storage duties, whereby validators must attest to the availability and integrity of the files they store.

The mechanism leverages [Proof-of-Replication (PoRep)](https://spec.filecoin.io/algorithms/pos/porep/) to ensure that validators have uniquely encoded and sealed copies of the data they agree to store, using the data itself, the identity of the storage provider, and the timestamp of sealing. This ensures the creation of unique cryptographic proof that confirms the data's existence at a specific time and under particular ownership, providing robust protection against data tampering and loss.

Following data sealing, validators must continuously prove the existence and availability of stored data using the PoSt method. This process involves regular and mandatory attestations of data persistence and availability without individual sector verification, instead verifying entire partitions in defined intervals. Validators are rewarded for successful storage attestations but are subject to penalties, such as slashes in the PoS system, for missed attestations. These penalties are enforced through on-chain mechanisms to maintain network integrity and validator compliance.

<mark style="color:red;">**The integration of PoS with PoSt does not alter the fundamental consensus rules of PoS regarding block production and validation but rather adds a layer of file storage responsibility that provides an additional revenue stream to validators.**</mark> <mark style="color:red;"></mark><mark style="color:red;">This model aims to harness the existing infrastructure and security of PoS while expanding the utility of the blockchain to encompass decentralized file-hosting services.</mark>

***

## The Motivation of Hybrid Consensus

The current PoS consensus mechanism is robust for transaction validation and block production. However, it needs to address the growing need for decentralized storage capabilities on the blockchain inherently, which are essential for broadening the range of decentralized applications (dApps) and services. The introduction of PoSt with PoS aims to integrate decentralized file storage into the existing PoS framework, enhancing the blockchain's functionality without altering the core consensus for block validation.

The first motivation for doing PoS-ST is to enhance the blockchain’s utility and economic viability. It aims to provide a comprehensive solution that supports the core functionalities of transaction processing and consensus building and extends the blockchain’s capabilities to include secure DePIN-based cloud storage. The validators will benefit from two revenue streams, which are essential for more stable and long-term participation in the network. This evolution is vital for the blockchain to remain competitive and relevant in an increasingly decentralized digital landscape.

\
The second motivation for upgrading to have a validator do the staking and storage duties is reinforcing the network's security and stability. In many DePIN-based cloud storage, the storage nodes perform a limited storage duty, where rules are only mandated by the storage protocol. The storage providers can also do as many nodes as they want, which tends to degrade the storage quality. Forcing staking and storage duties in Flashback guarantees the participation of good-quality providers, which must ensure a higher standard for blockchain validation and storage.

#### Trust and Decentralization

Integrating decentralized file storage into the blockchain's consensus layer enables a more trustless ecosystem. This reduces reliance on external storage solutions and increases data decentralization. This integration fosters a more resilient and censorship-resistant network, enhancing trust in the blockchain's capabilities.

We designed this consensus to support a decentralized, transparent, and on-chain commitment to the services running on our DePIN-based cloud storage. The PoS consensus from Ethereum is also known as its good decentralization factor, and forcing the storage providers to be validators reinforces the trust in their storage duties.

#### Economic Incentives for Validators

Incorporating PoSt commitments into validators' duties allows them to leverage their existing computational and storage hardware to earn additional income. This optimizes physical resources and provides a financial incentive for validators to support and maintain the network's storage capabilities, aligning their interests with the network's health and expansion.

The PoS-ST allows validators to participate in the storage duties while benefiting from the block validation. The storage providers will balance their profits between the staking and the storage revenues. The PoS-ST presents slashing mechanisms for their block validation and storage duties. A validator enabling storage will provide more services, improving the network's quality.

#### Scalability and Future Enhancements

The current implementation of PoS-ST uses standardized data encumbrances known as "Dencun blobs," which are a step toward more scalable storage solutions. The planned transition to non-interactive PoSt will enhance the system’s scalability and efficiency, enabling the network to handle larger data storage requests seamlessly.

This progression aligns with the blockchain’s long-term vision to support a wider array of decentralized services and applications, making the blockchain a platform for financial transactions and a robust layer for decentralized data services.

#### Addressing a Market Need

The integration of PoS-ST creates an open, customizable market for data storage within the blockchain environment. This market fills a critical gap in the current ecosystem. It establishes a new utility paradigm for blockchains, transforming them into multi-functional platforms that can meet diverse needs of modern digital economies.

The PoS-ST fills the gap and establishes solid foundations for innovative applications and services that will drive the mass adoption of the web3 ecosystem. The consensus offers the storage providers a straightforward profitability process while envisioning a variety of offers in a simple commitment mechanism.
