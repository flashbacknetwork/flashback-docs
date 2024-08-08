# Consensus: Proof-of-Stake-Spacetime

To achieve distributed consensus, each validator in Flashback must perform different checks on the blockchain. There are manifold distributed consensus mechanisms, such as the Nakamoto or [Slasher ](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm)consensus.

The Flashback network is a blockchain with on-chain and off-chain data storage. We have implemented a hybrid consensus approach known as <mark style="color:yellow;">**Proof-of-Stake-Spacetime (PoS-ST)**</mark> to validate both functionalities effectively\*\*.\*\*

This proposal introduces an upgrade to the current [Gasper's Proof-of-Stake (PoS)](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/) consensus mechanism by incorporating [Proof-of-Spacetime (PoSt)](https://spec.filecoin.io/algorithms/pos/post/) functionalities, aiming to enable decentralized file storage on an Ethereum Virtual Machine (EVM)-compatible blockchain. The core addition, termed PoS-ST, extends the validator's role to include transaction validation and storage duties, whereby validators must attest to the availability and integrity of the files they store.

The mechanism leverages [Proof-of-Replication (PoRep)](https://spec.filecoin.io/algorithms/pos/porep/) to ensure that validators have uniquely encoded and sealed copies of the data they agree to store, using the data itself, the identity of the storage provider, and the timestamp of sealing. This ensures the creation of unique cryptographic proof that confirms the data's existence at a specific time and under particular ownership, providing robust protection against data tampering and loss.

Following data sealing, validators must continuously prove the existence and availability of stored data using the PoSt method. This process involves regular and mandatory attestations of data persistence and availability without individual sector verification, instead verifying entire partitions in defined intervals. Validators are rewarded for successful storage attestations but are subject to penalties, such as slashes in the PoS system, for missed attestations. These penalties are enforced through on-chain mechanisms to maintain network integrity and validator compliance.

The integration of PoS with PoSt does not alter the fundamental consensus rules of PoS regarding block production and validation but rather adds a layer of file storage responsibility that provides an additional revenue stream to validators. This model aims to harness the existing infrastructure and security of PoS while expanding the utility of the blockchain to encompass decentralized file-hosting services.

***

## The Motivation of PoS-ST Consensus

The current PoS consensus mechanism is robust for transaction validation and block production. However, it needs to address the growing need for decentralized storage capabilities on the blockchain inherently, which are essential for broadening the range of decentralized applications (dApps) and services. The introduction of PoS-ST aims to integrate decentralized file storage into the existing PoS framework, enhancing the blockchain's functionality without altering the core consensus for block validation.

The motivation for upgrading to PoS-ST is driven by the desire to enhance the blockchain’s utility and economic viability. It aims to provide a comprehensive solution that supports the core functionalities of transaction processing and consensus building and extends the blockchain’s capabilities to include secure DePIN-based cloud storage. This evolution is essential for the blockchain to remain competitive and relevant in an increasingly decentralized digital landscape.

### Trust and Decentralization

Integrating decentralized file storage directly into the blockchain's consensus layer enables a more trustless ecosystem. This reduces reliance on external storage solutions and increases data decentralization. This integration fosters a more resilient and censorship-resistant network, enhancing trust in the blockchain's capabilities.

We designed this consensus to support a decentralized, transparent, and on-chain commitment to the services running on our DePIN-based cloud storage. The PoS consensus from Ethereum is also known as its good decentralization factor, and forcing the storage providers to be validators reinforces the trust in their storage duties.

### Economic Incentives for Validators

By incorporating PoSt commitments into the duties of validators, PoS-ST allows them to leverage their existing computational and storage hardware to earn additional fees. This optimizes physical resources and provides a financial incentive for validators to support and maintain the network's storage capabilities, aligning their interests with the network's health and expansion.

The PoS-ST allows validators to participate in the storage duties while benefiting from the block validation. The storage providers will balance their profits between the staking and the storage revenues. The PoS-ST presents slashing mechanisms for their block validation and storage duties. A validator enabling storage will provide a higher degree of services, improving the network's quality.

### Scalability and Future Enhancements

The current implementation of PoS-ST uses standardized data encumbrances known as "Dencun blobs," which are a step toward more scalable storage solutions. The planned transition to non-interactive PoSt will enhance the system’s scalability and efficiency, enabling the network to handle larger data storage requests seamlessly.

This progression aligns with the blockchain’s long-term vision to support a wider array of decentralized services and applications, making the blockchain a platform for financial transactions and a robust layer for decentralized data services.

### Addressing a Market Need

The integration of PoS-ST creates an open, customizable market for data storage within the blockchain environment. This market fills a critical gap in the current ecosystem and establishes a new utility paradigm for blockchains, transforming them into multi-functional platforms that can meet diverse needs of modern digital economies.

The implementation of PoS-ST fills the gap and establishes solid foundations for innovative applications and services that will drive the mass adoption of the web3 ecosystem. The consensus offers the storage providers a straightforward profitability process while envisioning a variety of offers in a simple commitment mechanism.

***

## PoS-ST Specifications

This section outlines the detailed technical changes to the network's architecture, including adjustments to block validation, consensus rules, and node requirements with the integration of the PoS-ST mechanism.

### Cryptographic Techniques using zk-SNARKS

The PoS-ST protocol incorporates Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge (zk-SNARKs) to enable validators to prove the integrity and ongoing availability of the data they store without revealing the actual data:

* **Functionality**: zk-SNARKs allow validators to prove that they possess specific data by generating and submitting proofs that demonstrate data integrity and possession while keeping the actual data private and without any interaction between the prover (validator) and the verifier (network).
* **Implementation in PoST**: Validators use zk-SNARKs to create compact, non-interactive proofs for data integrity. These proofs are integrated into the network's existing consensus mechanisms, ensuring they are scalable and minimally invasive to network performance.

### Application in Windowed Proof

PoS-ST uses windowed proofs to maintain continuous verification of data integrity over time:

* **Proof Creation**: Upon initiating a storage contract, validators generate a zk-SNARK proof that establishes the initial data storage conditions. Validators must then produce subsequent proofs periodically, as the storage contract stipulates, to demonstrate ongoing compliance and data integrity.
* **Proof Verification**: These proofs are submitted in response to periodic challenges based on the windows defined by each contract. The network verifies these proofs using decentralized verification mechanisms, ensuring validators adhere to their storage obligations without requiring full data disclosure.

### Dynamic Proof Window Duration

The flexibility of proof windows is a key feature of PoS-ST:

* **Customization**: The duration of proof windows can be customized in the validator's storage contract, allowing validators to adapt their resource allocation to the requirements of the contract issuer. This feature provides significant flexibility and optimizes network resource utilization.
* **Adaptation and Efficiency**: This customization helps the network efficiently manage resource distribution and accommodate varying storage needs, ranging from dynamic short-term data to static long-term storage.

### Penalty Mechanisms from Existing PoS Systems

PoS-ST integrates penalty mechanisms familiar to traditional PoS validators:

* **Enforcement and Compliance**: Validators who fail to submit valid proofs within the specified windows are subject to penalties, including the potential loss of staked tokens or reduced opportunities to participate in future proofs.
* **Network Governance**: The specifics of these penalties, including severity and conditions, are governed by the network's consensus protocols. Changes to the penalty system can be proposed and implemented through protocol amendments, ensuring they remain fair and effective.

### Validator's Node Requirements

Nodes participating in PoS-ST must meet additional hardware and software requirements to handle the increased computational load:

* **Hardware Specifications**: Validators require enhanced storage capabilities to manage the data for which they are responsible. Additionally, sufficient computational power is needed to efficiently generate and verify zk-SNARK proofs.
* **Software Specifications**: Nodes must run software that supports zk-SNARK generation and verification, integrated seamlessly with the blockchain's existing consensus software.

### Integration with the Dencun Data Availability Layer

Proofs generated by validators are pushed as blobs on the Dencun data availability layer, ensuring that proofs are accessible and verifiable by the entire network without congesting the blockchain with large data files.
