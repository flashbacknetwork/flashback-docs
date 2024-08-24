# Minimal Requirements

## Minimal Hardware Requirements for Staking

As Flashback inherits from the Ethereum specifications, the network can support light, complete, and archive nodes. The validator cannot make the storage duties available. Flashback does not have the history of Ethereum and can reduce certain specifications. The minimal hardware requirements must then evolve with the growth of the Flashback ecosystem. &#x20;

| Category          | Light Node          | Full Node           | Archive Node         |
| ----------------- | ------------------- | ------------------- | -------------------- |
| CPU               | 2 cores - 4 threads | 4 cores - 8 threads | 8 cores - 16 threads |
| RAM               | 2 GB                | 8 GB                | 32 GB                |
| Storage           | 50 GB SSD           | 500 GB SSD          | 2 TB NVMe            |
| Network Bandwidth | 10 Mbps             | 25 Mbps             | 100 Mbps             |

## Minimal Hardware Requirements for Storage

**A** Flashback validator performing storage duties will operate the [proof-of-stake spacetime (PoS-ST)](../../../learn/consensus-proof-of-stake-spacetime.md). Flashback needs to integrate storage in block generation and validation like Filecoin, which removes some processes and responsibilities compared to the protocol. Nonetheless, the Proof-of-Spacetime (PoSt) in the PoS-ST demands considering specific hardware requirements to achieve the zero-knowledge procedure of PoSt properly. \
The minimal hardware requirements also depend highly on the [sealing rate](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/sealing-rate.md), which means how the validator wants to perform the[ sealing pipeline](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/sealing-pipeline/). The following considers the minimal hardware requirements for a single-sealing rate (sealing sector by sector, 32 GiB sector). We also consider the transformation of a PoS-only validator into a PoS-ST validator according to the node client (light, full, archive).&#x20;

<table><thead><tr><th width="182">Category</th><th width="189">Light Node</th><th width="187">Full Node</th><th>Archive Node</th></tr></thead><tbody><tr><td>CPU</td><td>8 cores - 12 threads</td><td>10 cores - 16 threads</td><td>12 cores - 24 threads</td></tr><tr><td>RAM</td><td>256 GB</td><td>256 GB</td><td>256 GB</td></tr><tr><td>Storage (Staking)</td><td>50 GB SSD</td><td>500 GB SSD</td><td>2 TB NVMe</td></tr><tr><td>Storage (Sealing)</td><td>2 TB NVMe</td><td>2 TB NVMe</td><td>2 TB NVMe</td></tr><tr><td>Storage (Files)</td><td>1 TB HDD/SSD/NVMe</td><td>1 TB HDD/SSD/NVMe</td><td>1 TB HDD/SSD/NVMe</td></tr><tr><td>GPU</td><td>12 GB VRAM</td><td>12 GB VRAM</td><td>12 GB VRAM</td></tr><tr><td>Network Bandwidth</td><td>1 Gbps</td><td>1 Gbps</td><td>1 Gbps</td></tr></tbody></table>

## Additional Considerations

* **Backup and Security**: Since validators must keep their private keys secure, consider using hardware security modules (HSMs) or secure offline storage (cold wallets) for private keys.
* **Redundancy**: For those seeking to operate a highly available node, consider setting up failover systems or backup internet connections to ensure continuous operation.
* **Regular Upgrade**: The Flashback network is constantly evolving. Increasing traffic and user numbers will change the minimum requirements. It's essential to adapt accordingly and regularly update your customers and hardware.
