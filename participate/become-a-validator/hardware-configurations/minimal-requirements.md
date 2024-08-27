# Minimal Requirements

## Network Protocol Clients

As Flashback inherits from the Ethereum specifications, the network can support light, complete, and archive nodes. The validator cannot make the storage duties available. Flashback does not have the history of Ethereum and can reduce certain specifications. The minimal hardware requirements must then evolve with the growth of the Flashback ecosystem. &#x20;

| Category          | Light Node          | Full Node           | Archive Node         |
| ----------------- | ------------------- | ------------------- | -------------------- |
| CPU               | 2 cores - 4 threads | 4 cores - 8 threads | 8 cores - 16 threads |
| RAM               | 2 GB                | 8 GB                | 32 GB                |
| Storage           | 50 GB SSD           | 500 GB SSD          | 2 TB NVMe            |
| Network Bandwidth | 10 Mbps             | 25 Mbps             | 100 Mbps             |

## Storage Duties (PoS-ST Nodes)

**A** Flashback validator performing storage duties will operate the [proof-of-stake spacetime (PoS-ST)](../../../learn/consensus-proof-of-stake-spacetime.md). Flashback needs to integrate storage in block generation and validation like Filecoin, which removes some processes and responsibilities compared to the protocol. Nonetheless, the Proof-of-Spacetime (PoSt) in the PoS-ST demands considering specific hardware requirements to properly achieve the [Sector Proving](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/). \
The minimal hardware requirements also depend heavily on the sealing rate and snap dealy on the [sealing rate](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/sealing-rate.md) and [snapdeal rate](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/snapdeal-rate.md). The following considers the minimal hardware requirements for a single-sealing rate (sealing sector by sector, 64 GiB sector).&#x20;

<table><thead><tr><th width="182">Category</th><th width="293">Full Node</th><th>Archive Node</th></tr></thead><tbody><tr><td>CPU</td><td>12 cores</td><td>12 cores</td></tr><tr><td>RAM</td><td>264 GB</td><td>288 GB</td></tr><tr><td>Storage (System + Staking)</td><td>500 GB SSD</td><td>2 TB NVMe</td></tr><tr><td>Storage (Sector Proving)</td><td>1 TB NVMe</td><td>1 TB NVMe</td></tr><tr><td>Storage (Files)</td><td>Min. 100 GB (up to Provider to add more)</td><td>Min. 100 GB (up to Provider to add more)</td></tr><tr><td>GPU</td><td>12 GB VRAM</td><td>12 GB VRAM</td></tr><tr><td>Network Bandwidth</td><td>1 Gbps</td><td>1 Gbps</td></tr></tbody></table>

The following table resumes the requirements for every steps of the sealing and snapdeal pipelines with 64 GiB:

| Operation              | CPU used         | VRAM   | RAM       | NVMe Space |
| ---------------------- | ---------------- | ------ | --------- | ---------- |
| AddPiece               | All Cores        | -      | 0.2GiB    | 64 GiB     |
| PreCommit 1            | 1 Core           | -      | 64GiB     | 768 GiB    |
| PreCommit 2            | All Cores or GPU | 5 GiB  | 30GiB     | 64 GiB     |
| Commit 1               | 1 Core           | -      | -         | 128 GiB    |
| Commit 2               | All Cores or GPU | 11 GiB | \~ 192GiB | 2 GiB      |
| Unsealing              | 1 Core           | -      | 64GiB     | -          |
| Replica Update         | 1 Core           | 5 GiB  | 64GiB     | 64 GiB     |
| Prove Replica Update 1 | All Cores or GPU | -      | -         | 768 GiB    |
| Prove Replica Update 2 | All Cores or GPU | 11 GiB | \~ 192GiB | 64 GiB     |
| WindowPoSt             | All Cores or GPU | 11 GiB | 96GiB     | 64 GiB     |

## Additional Considerations

* **Backup and Security**: Since validators must keep their private keys secure, consider using hardware security modules (HSMs) or secure offline storage (cold wallets) for private keys.
* **Redundancy**: For those seeking to operate a highly available node, consider setting up failover systems or backup internet connections to ensure continuous operation.
* **Regular Upgrade**: The Flashback network is constantly evolving. Increasing traffic and user numbers will change the minimum requirements. It's essential to adapt accordingly and regularly update your customers and hardware.
