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
