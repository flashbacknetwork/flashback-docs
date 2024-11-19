# CC Sector Update

In Filecoin, **SnapDeals** is specifically designed to add deals to **Committed Capacity (CC) sectors**. A CC sector is an empty sector that a storage provider has sealed and committed to the network. It doesn't contain any user data yet—effectively, it's a placeholder sector.

Since CC sectors do not initially contain real data, they are flexible and can later be filled with client data (deals). This flexibility is crucial for SnapDeals because the process involves adding new deal data into an already sealed sector without resealing the entire sector from scratch.

On the other hand, once a sector contains deal data (making it a "deal sector"), it is sealed in a specific cryptographic state that includes commitments to the data it holds. Any change to the data would require resealing the sector to produce a new Proof-of-Replication (PoRep). <mark style="color:red;">**This is why deal sectors are unsuitable for SnapDeals**</mark>; they already have their data commitments finalized, and altering this state would break the proofs.

Section Table

<table><thead><tr><th width="227">Section</th><th>Summary</th></tr></thead><tbody><tr><td><a href="snapdeal-pipeline/"><strong>SnapDeal Pipeline</strong></a></td><td><em>SnapDeal is the process of updating a CC sector with true deals and has its algorithms and constraints.</em></td></tr><tr><td><a href="snapdeal-rate.md"><strong>SnapDeal Rate</strong></a></td><td><em>Similar to the rate in the sealing pipeline, the rate of SnapDeal depends on every step, and it is good to comprehend it.</em></td></tr></tbody></table>

***

Let's explore how Filecoin allows to update the CC sectors composed of "fake" deals by exploring the SnapDeal process!
