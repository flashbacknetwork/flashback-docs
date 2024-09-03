# CC Update with SnapDeals

In Filecoin, **SnapDeals** is specifically designed to add deals to **Committed Capacity (CC) sectors**. A CC sector is an empty sector that a storage provider has sealed and committed to the network, but it doesn't contain any user data yet—effectively, it's a placeholder sector.

## Why Only CC Sectors for SnapDeals?

* **CC Sector Characteristics**: Since CC sectors do not contain any deal data initially, they are flexible and can later be filled with client data (deals). This flexibility is crucial for SnapDeals because the process involves adding new deal data into an already sealed sector without having to reseal the entire sector from scratch.
* **Deal Sectors Are Immutable**: On the other hand, once a sector contains deal data (making it a "deal sector"), it is sealed in a specific cryptographic state that includes commitments to the data it holds. Any change to the data would require resealing the sector to produce a new Proof-of-Replication (PoRep). This is why deal sectors are not suitable for SnapDeals; they already have their data commitments finalized, and altering this state would break the proofs.

Let's explore how Filecoin allows to update the CC sectors composed of "fake" deals by exploring the [SnapDeal pipeline](snapdeal-pipeline/) and [SnapDeal rate](snapdeal-rate.md).&#x20;

