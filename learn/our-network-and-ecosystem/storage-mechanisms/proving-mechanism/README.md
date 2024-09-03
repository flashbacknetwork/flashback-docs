# Sector: A Storage Unit to Prove

In the Filecoin network, a "sector" is a fundamental unit of storage that a storage provider commits to the network to use in deals with clients. Essentially, sectors are how storage is organized and sold in Filecoin. Here’s a breakdown of what a sector involves and its role in the network:

## Definition and Purpose

* **Size and Configuration**: The Filecoin protocol defines sectors. Common sizes are 32 GiB ([gibibytes](https://www.techtarget.com/searchstorage/definition/gibibyte-GiB)) and 64 GiB. The size determines how much data can be stored in a single sector.
* **Commitment to the Network**: Storage providers commit these sectors to the Filecoin blockchain through a process known as "sealing." Sealing is a cryptographic process that prepares the sector for storage by encoding the data and generating proofs of replication (PoRep) to prove that the data is uniquely stored.

## Role in Filecoin

* **Storage Deals**: When a client and a storage provider agree on a storage deal, the provider accepts the contract, and the data is stored in one or more sectors. Each sector is dedicated to a particular deal or could be shared among multiple deals, depending on the agreement and the sector size.
* **Proving Storage**: Sectors are critical for storage providers to prove that they reliably store data. Providers must submit regular proofs, known as Proofs of Spacetime (PoSt), which attest that each committed sector correctly stores its data over time.
* **Lifecycle**: A sector's lifecycle in Filecoin includes pledging (committing the sector), sealing (preparing and proving the storage of data), storing (the duration of the storage deal), and, eventually, sector removal or re-use after a deal concludes.

## Section Summary

### [Importance of Proving](importance-of-proving.md)

_Discover why generating proofs of sector existence is essential in a decentralized storage network._

### [Initial Sealing (PoRep)](proof-of-replication-porep.md)

_The steps of every sector's proof-of-replication (PoRep) to make the storage more transparent and traceable._

### [Availability Checkup (PoSt)](./#sector-availability-checkup-post)

_The different steps of every sector's proof-of-spacetime (PoSt) to ensure a reliable, available, and secure storage ecosystem._

### [Availability Checkup (PoSt)](./#sector-availability-checkup-post)

_The different steps of every sector's proof-of-spacetime (PoSt) to ensure a reliable, available, and secure storage ecosystem._
