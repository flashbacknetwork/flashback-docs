# Hardware Requirements

**A** Flashback validator performing storage duties will operate the [proof-of-stake spacetime (PoS-ST)](../../../learn/consensus-proof-of-stake-spacetime.md). Flashback needs to integrate storage in block generation and validation like Filecoin, which removes some processes and responsibilities compared to the protocol. Nonetheless, the Proof-of-Spacetime (PoSt) in the PoS-ST demands considering specific hardware requirements to properly achieve the [Sector Management](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/). \
The minimal hardware requirements also depend heavily on the sealing rate and snap dealy on the [sealing rate](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/sealing-rate.md) and [snapdeal rate](../../../learn/our-network-and-ecosystem/storage-mechanisms/proving-mechanism/cc-sector-update/snapdeal-rate.md). The following considers the minimal hardware requirements for a single-sealing rate (sealing sector by sector, 64 GiB sector).&#x20;

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

