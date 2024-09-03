# Sealing Pipeline

The sealing pipeline in Filecoin is a sophisticated, multi-stage process essential for storage providers to securely encrypt and commit data to the network. It ensures that data is not only stored securely but also verifiable through cryptographic proofs that confirm its continued existence and integrity over time.

The sealing process comprises several distinct phases, each with specific hardware requirements and performance considerations:

## [**AddPiece (AP)**](addpiece-ap.md)

_This initial phase involves taking the raw data in CAR-file format and preparing it for the cryptographic processes that follow. Data is written to the sealing scratch space, preparing for the next phase, PreCommit 1._&#x20;

## [**PreCommit 1 (PC1)**](precommit-1-pc1.md)

_This phase is crucial for transforming the raw data into a cryptographically secure format through the Proof-of-Replication (PoRep) process. The data undergoes SDR (Seal Data Replica) encoding, creating multiple data layers and enhancing security._

## [**PreCommit 2 (PC2)**](./#precommit-2-pc2)

_Validates the encoding done by PC1 using the Poseidon hashing algorithm to create a Merkle Tree DAG of the encoded data. It transfers the entire scratch space prepared in PC1 to PC2._

## [**WaitSeed**](waitseed.md)

_The blockchain mandates a built-in waiting period to enhance security measures between the sealing and committing phases. The system waits for several blockchain epochs before proceeding to the next step, ensuring no premature commitments._

## [Commit 1 (C1)](commit-1-c1-and-commit-2-c2.md)

_An intermediate phase that performs the necessary preparations for generating a zk-SNARK proof will later be used to prove that the data has been correctly replicated and stored._

## [Commit 2 (C2)](commit-2-c2.md)

_Commit 2 (C2) is the final phase in the sealing pipeline where the zk-SNARK proof is generated. This proof certifies that the data has been correctly replicated and stored following Filecoin's protocol._

## [On-Chain Commitment](on-chain-commitment.md)

_It involves submitting the zk-SNARK proof to the Filecoin blockchain, where it is verified and recorded, confirming the storage provider's proof of data replication and storage, which secures their storage deal rewards and maintains network integrity._
