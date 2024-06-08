---
IP: 2
title: Upgrade to Proof-of-Stake-Spacetime (PoS-ST) Consensus Mechanism
author: Giacomo Milligan (@giaki3003) <giacomo.milligan@thenephelecloud.com>
discussions-to: TBD
status: Draft
type: Standards Track
category: Core
created: 2024-04-30
requires: (list any IPs this IP depends on)
---

Each validator in Nephele must perform different checks on the blockchain to achieve distributed consensus. There are manifold distributed consensus mechanisms such as the Nakamoto or [Slasher ](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm)consensus.&#x20;

The Nephele network functions both as a blockchain and a data storage medium. We have implemented a hybrid consensus approach known as **Proof-of-Stake-Spacetime (PoS-ST)** to validate both functionalities effectively.

PoS-ST extends [Gasper's Proof-of-Stake (PoS)](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/) consensus mechanism, incorporating space-time validation to enable decentralized file storage on an EVM-compatible blockchain.&#x20;

Unlike standard PoS, which primarily secures network consensus through validators' staked tokens, PoS-ST introduces an additional layer where validators also attest to the persistence and availability of files they store. This mechanism does not replace but builds on existing PoS functionalities by adding file storage duties to which validators can subscribe. Validators fulfilling these storage responsibilities are compensated, providing them with an additional revenue stream.&#x20;

This approach leverages the existing infrastructure of PoS to facilitate decentralized file hosting, enhancing the utility of the blockchain while offering validators a new avenue for earnings through their contributions to network storage and bandwidth.


## Abstract

This proposal introduces an upgrade to the current Proof-of-Stake (PoS) consensus mechanism by incorporating Proof-of-Spacetime (PoSt) functionalities, aiming to enable decentralized file storage on an Ethereum Virtual Machine (EVM)-compatible blockchain. The core addition, termed PoS-ST, extends the validator's role to include not just transaction validation but also storage duties, whereby validators must attest to the availability and integrity of the files they store.

The mechanism leverages Proof-of-Replication (PoRep) to ensure that validators have uniquely encoded and sealed copies of the data they agree to store, using the data itself, the identity of the storage provider, and the timestamp of sealing. This ensures the creation of a unique cryptographic proof, which confirms the data's existence at a specific time and under specific ownership, providing robust protection against data tampering and loss.

Following data sealing, validators are required to continuously prove the existence and availability of stored data using the Proof-of-Spacetime (PoSt) method. This process involves regular and mandatory attestations of data persistence and availability without individual sector verification, instead verifying entire partitions in defined intervals. Validators are rewarded for successful storage attestations but are subject to penalties, such as slashes in the PoS system, for missed attestations. These penalties are enforced through on-chain mechanisms to maintain network integrity and validator compliance.

The integration of PoS with PoSt does not alter the fundamental consensus rules of PoS regarding block production and validation but rather adds a layer of file storage responsibility that provides an additional revenue stream to validators. This model aims to harness the existing infrastructure and security of PoS while expanding the utility of the blockchain to encompass decentralized file hosting services.

## Motivation

The current Proof-of-Stake (PoS) consensus mechanism is robust for transaction validation and block production. However, it does not inherently address the growing need for decentralized storage capabilities on the blockchain, which are essential for broadening the range of decentralized applications (dApps) and services. The introduction of PoS-ST aims to integrate decentralized file storage into the existing PoS framework, enhancing the blockchain's functionality without altering the core consensus for block validation.

**Trust and Decentralization:** Integrating decentralized file storage directly into the blockchain's consensus layer enables a more trustless ecosystem, reducing reliance on external storage solutions and increasing the decentralization of data. This integration fosters a more resilient and censorship-resistant network, enhancing the overall trust in the blockchain's capabilities.

**Economic Incentives for Validators:** By incorporating Proof-of-Spacetime (PoSt) commitments into the duties of validators, PoS-ST allows them to leverage their existing computational and storage hardware to earn additional fees. This not only optimizes the use of physical resources but also provides a financial incentive for validators to support and maintain the network's storage capabilities, aligning their interests with the network's health and expansion.

**Scalability and Future Enhancements:** The current implementation of PoS-ST uses standardized data encumbrances known as "dencun blobs," which are a step toward more scalable storage solutions. Looking ahead, the planned transition to non-interactive PoSt will further enhance the system’s scalability and efficiency, enabling the network to handle larger volumes of data storage requests seamlessly. This progression is aligned with the blockchain’s long-term vision to support a wider array of decentralized services and applications, making the blockchain not just a platform for financial transactions but also a robust layer for decentralized data services.

**Addressing a Market Need:** The integration of PoS-ST creates an open, customizable market for data storage within the blockchain environment. This market not only fills a critical gap in the current ecosystem but also establishes a new utility paradigm for blockchains, transforming them into multi-functional platforms that can meet diverse needs of modern digital economies.

In summary, the motivation for upgrading to PoS-ST is driven by the desire to enhance the blockchain’s utility and economic viability. It aims to provide a comprehensive solution that not only supports the core functionalities of transaction processing and consensus building but also extends the blockchain’s capabilities to include secure, decentralized data storage. This evolution is essential for the blockchain to remain competitive and relevant in an increasingly decentralized digital landscape.

This section articulates why the addition of PoS-ST is a strategic enhancement to the existing PoS mechanism, focusing on the benefits of integrated decentralized file storage and the broader implications for the blockchain's functionality and stakeholder incentives. If you have any more specifics or adjustments to add, please let me know!

Given the detailed description you provided regarding cryptographic techniques and dynamic proof window durations, I'll structure the Specification section of the IP-2 document to encompass these key elements:

---

## Specification

This section outlines the detailed technical changes to the network's architecture, including adjustments to block validation, consensus rules, and node requirements with the integration of the PoS-ST mechanism.

### 1. Cryptographic Techniques Using zk-SNARKs
The PoS-ST protocol incorporates Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge (zk-SNARKs) to enable validators to prove the integrity and ongoing availability of the data they store without revealing the actual data:

- **Functionality**: zk-SNARKs allow validators to prove that they possess specific data by generating and submitting proofs that demonstrate data integrity and possession while keeping the actual data private and without any interaction between the prover (validator) and the verifier (network).
  
- **Implementation in PoST**: Validators use zk-SNARKs to create compact, non-interactive proofs for data integrity. These proofs are integrated into the network's existing consensus mechanisms, ensuring they are both scalable and minimally invasive to network performance.

### 2. Application in Windowed Proofs
PoS-ST uses windowed proofs to maintain continuous verification of data integrity over time:

- **Proof Creation**: Upon initiating a storage contract, validators generate a zk-SNARK proof that establishes the initial conditions of the data storage. Validators must then produce subsequent proofs periodically, as stipulated by the storage contract, to demonstrate ongoing compliance and data integrity.

- **Proof Verification**: These proofs are submitted in response to periodic challenges based on the windows defined by each contract. The network verifies these proofs using decentralized verification mechanisms, ensuring validators adhere to their storage obligations without requiring full data disclosure.

### 3. Dynamic Proof Window Duration
The flexibility of proof windows is a key feature of PoS-ST:

- **Customization**: The duration of proof windows can be customized for each storage contract, allowing validators to adapt their resource allocation to the requirements of the contract issuer. This feature provides significant flexibility and optimizes network resource utilization.

- **Adaptation and Efficiency**: This customization helps the network efficiently manage resource distribution and accommodate varying storage needs, ranging from dynamic short-term data to static long-term storage.

### 4. Penalty Mechanisms from Existing PoS Systems
PoS-ST integrates penalty mechanisms familiar to traditional PoS validators:

- **Enforcement and Compliance**: Validators who fail to submit valid proofs within the specified windows are subject to penalties, including the potential loss of staked tokens or reduced opportunities to participate in future proofs.

- **Network Governance**: The specifics of these penalties, including severity and conditions, are governed by the network's consensus protocols. Changes to the penalty system can be proposed and implemented through amendments to the protocols, ensuring they remain fair and effective.

### 5. Node Requirements
Nodes participating in PoS-ST must meet additional hardware and software requirements to handle the increased computational load:

- **Hardware Specifications**: Validators require enhanced storage capabilities to manage the data for which they are responsible. Additionally, sufficient computational power is needed to generate and verify zk-SNARK proofs efficiently.

- **Software Specifications**: Nodes must run software that supports zk-SNARK generation and verification, integrated seamlessly with the blockchain's existing consensus software.

### 6. Integration with the Dencun Data Availability Layer
Proofs generated by validators are pushed as blobs on the dencun data availability layer, ensuring that proofs are accessible and verifiable by the entire network without congesting the blockchain with large data files.

## Rationale
Discussion of the design decisions involved in the upgrade, including why certain trade-offs were chosen and how they benefit the overall functionality and security of the network. This will cover alternative designs that were considered and why the proposed approach was preferred.

## Backwards Compatibility
Analysis of how the changes will affect existing deployments, including the impact on current transactions and contracts. This section will detail the steps needed to transition from the current PoS to PoS-ST without disrupting network operations.

## Test Cases
Provide test cases to illustrate how the new rules can be verified. This includes scenarios covering both expected operation and edge cases to ensure robustness.

## Reference Implementation
(Optional) A reference implementation to demonstrate the proposed changes. This could include links to repositories containing code that implements PoS-ST, or patches to existing Ethereum client implementations.

## Security Considerations
Discussion of the security implications of introducing PoS-ST to the Ethereum network, addressing potential risks and how they are mitigated. Special attention should be paid to new attack vectors opened by space-time components.

## Copyright Waiver
Copyright and related rights waived via CC0.




# Consensus: Proof-of-Stake-Spacetime

Each validator in Nephele must perform different checks on the blockchain to achieve distributed consensus. There are manifold distributed consensus mechanisms such as the Nakamoto or [Slasher ](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm)consensus.&#x20;

The Nephele network functions both as a blockchain and a data storage medium. We have implemented a hybrid consensus approach known as **Proof-of-Stake-Spacetime (PoS-ST)** to validate both functionalities effectively.

PoS-ST extends [Gasper's Proof-of-Stake (PoS)](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/) consensus mechanism, incorporating space-time validation to enable decentralized file storage on an EVM-compatible blockchain.&#x20;

Unlike standard PoS, which primarily secures network consensus through validators' staked tokens, PoS-ST introduces an additional layer where validators also attest to the persistence and availability of files they store. This mechanism does not replace but builds on existing PoS functionalities by adding file storage duties to which validators can subscribe. Validators fulfilling these storage responsibilities are compensated, providing them with an additional revenue stream.&#x20;

This approach leverages the existing infrastructure of PoS to facilitate decentralized file hosting, enhancing the utility of the blockchain while offering validators a new avenue for earnings through their contributions to network storage and bandwidth.

## Nephele: An Ethereum Fork

Nephele is firstly is a fork of the Ethereum codebase. This means the blockchain of the Nephele network inherits all the underlying primitives of the Ether ecosystem. For instance, it will be possible to deploy smart contracts on the Nephele network, to create non-fungible tokens (NFTs), to create tokens, or to build layer-2 solutions.&#x20;

Since Nephele is a decentralized entity, all network participants must independently verify this consensus. We chose the Ethereum codebase because of its legitimacy and efficiency over the last few years. The consensus supported numerous attacks, and the technology is one of the most used in the cryptocurrency ecosystem.&#x20;

Hence, Nephele is using Gasper consensus (Proof-of-Stake) \[27]. Combining these two consensus algorithms allows Nephele to:

* Avoid the weak subjectivity issue \[23] inherent with all PoS systems. For instance, this ensures that new nodes entering the network without previous knowledge of the blockchain can indeed achieve the same state shared by existing nodes on the network, as long as there is no malignant party controlling  23  of the network.
* Enforce data replication and integrity for all file storage (FS) contracts. For instance, a node cannot pledge data from an already-accepted FS contract (committed by a user) without having access to that data locally. Thus ensuring the security and integrity of stored files.

\


The Gasper consensus divides time into epochs and slots, where an epoch contains a fixed number of slots. A slot is a potential opportunity for a block to be added to the blockchain. This means every blockchain validator is assigned to a slot by the committee, where the committee is a group of validators chosen to vote on the proposed blocks to achieve consensus. For each epoch, the network elects a new committee. If the validator misses their slot, the next one will adhere to the protocol. The validators are selected through a pseudorandom process, considering the number of tokens they are staking.&#x20;

\


While vanilla PoS systems are extensively documented and reviewed, we will focus on the extra subset of rules added to the network, which we call the extended consensus (EC). This consensus is integrated into the existing system, leveraging the advantages that the Beacon Chain \[24] brings such as attestations or Decentralised Autonomous Organisation entropy (RanDAO) \[25]. The EC enhances the robustness and functionality of the network, ensuring improved performance and security.

### c - The Extended Consensus

The EC can be defined with two cryptographic primitives:

* Proof-of-SpaceTime (PoSt) that allows a storage and staking node to prove it has access to a certain amount of bytes at a certain time. The underlying cryptographic primitives are zero-knowledge SNARK (ZK-SNARK) \[28], which heavily benefit from optimized libraries and graphic processing unit (GPU) support such as rust-fil-proofs \[29], which we will be leveraging.
* Proof-of-Replication (PoRep) that allows a storage and staking node to prove it has received a copy of the bytes allocated by the FS contract.

\


The network must ensure the liveness of files, requiring validators to submit recurring PoSts proofs over time stamped windows. To achieve this, we have then implemented the WindowPoSt, a derivative solution of the standard PoSt. The mathematical assumptions backing this process assume that the bytes allotted by the FS contract are not easily exchangeable (or not until the time stamped window expires) between different machines, thus, mitigating the possibility of Timing Attacks \[30]. The implementation of the EC is necessary to guarantee a secure, stable, and decentralized storage ecosystem within the network.&#x20;

\


\
