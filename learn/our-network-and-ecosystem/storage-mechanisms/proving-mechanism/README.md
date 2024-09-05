# Sector: The Storage Unit

In the Filecoin network, a "sector" is a fundamental unit of storage that a storage provider commits to the network to use in deals with clients. Essentially, sectors are how storage is organized and sold in Filecoin. Here’s a breakdown of what a sector involves and its role in the network:

#### Definition and Purpose

* **Size and Configuration**: The Filecoin protocol defines sectors. Common sizes are 32 GiB ([gibibytes](https://www.techtarget.com/searchstorage/definition/gibibyte-GiB)) and 64 GiB. The size determines how much data can be stored in a single sector.
* **Commitment to the Network**: Storage providers commit these sectors to the Filecoin blockchain through a process known as "sealing." Sealing is a cryptographic process that prepares the sector for storage by encoding the data and generating proofs of replication (PoRep) to prove that the data is uniquely stored.

#### Role in Filecoin

* **Storage Deals**: When a client and a storage provider agree on a storage deal, the provider accepts the contract, and the data is stored in one or more sectors. Each sector is dedicated to a particular deal or could be shared among multiple deals, depending on the agreement and the sector size.
* **Proving Storage**: Sectors are critical for storage providers to prove that they reliably store data. Providers must submit regular proofs, known as Proofs of Spacetime (PoSt), which attest that each committed sector correctly stores its data over time.
* **Lifecycle**: A sector's lifecycle in Filecoin includes pledging (committing the sector), sealing (preparing and proving the storage of data), storing (the duration of the storage deal), and, eventually, sector removal or re-use after a deal concludes.

## Section Table

<table><thead><tr><th width="227">Section</th><th>Summary</th></tr></thead><tbody><tr><td><a href="importance-of-proving.md"><strong>Importance of Proving</strong></a></td><td><em>Discover why generating proofs of sector existence is essential in a decentralized storage network.</em></td></tr><tr><td><a href="committed-capacity-cc.md"><strong>Committed Capacity (CC)</strong></a></td><td><em>At the start of storage provision, committed capacity informs the network of your storage availability by creating placeholders called CC sectors.</em></td></tr><tr><td><a href="./#initial-sealing-porep"><strong>Initial Sealing (PoRep)</strong></a></td><td><em>The steps of every sector's proof-of-replication (PoRep) to make the storage more transparent and traceable.</em></td></tr><tr><td><a href="proof-of-spacetime-post.md"><strong>Availability Verification (PoSt)</strong></a></td><td><em>The different steps of every sector's proof-of-spacetime (PoSt) to ensure a reliable, available, and secure storage ecosystem.</em></td></tr><tr><td><a href="cc-update-with-snapdeal/"><strong>CC Update with SnapDeal</strong></a></td><td><em>The storage node with CC sectors has been sealed without fake deals. SnapDeal updates the CC sectors with true deals.</em></td></tr><tr><td><a href="storage-providers-collateral.md"><strong>Storage Providers' Collateral</strong></a></td><td><em>The Filecoin protocol requires different collateral from the storage providers to operate efficiently.</em></td></tr><tr><td><a href="slashing.md"><strong>Slashing</strong></a></td><td><em>Penalties are essential to maintain a high level of quality of services and commitment to the protocol.</em></td></tr></tbody></table>

***

The sector is an essential brick of the Filecoin protocol and theonly way to make decentralized data storage at a consensus level. Let's navigate in this elementary unit of storage!
