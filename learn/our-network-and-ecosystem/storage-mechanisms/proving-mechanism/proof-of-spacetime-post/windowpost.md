# WindowPoSt

Windowed Proof of Spacetime (WindowPoSt) is a specific implementation of the Proof of Spacetime used in the Filecoin network, tailored to verify the ongoing data storage across vast numbers of sectors managed by storage providers.&#x20;

***

## General Concept introduction

### **Purpose**

WindowPoSt verifies that storage providers continuously store the data they have committed to over time. It is the primary mechanism by which the network periodically checks all storage providers. To ensure continuous data integrity, each storage sector—whether 32 GiB or 64 GiB—is verified daily during a 24-hour proving period.

### **Process**

Storage providers must submit these proofs for all their stored data every 24-hour cycle. This proving period is subdivided into 48 non-overlapping 30-minute intervals, known as deadlines. Storage sectors are organized into partitions, and each partition is assigned a deadline within which all its sectors must be verified.

### **Structure**

A storage provider's data is organized into partitions, each containing up to 2349 sectors due to the proof system's limits. Storage providers must submit a separate proof for each partition they maintain, ensuring comprehensive coverage of all stored data.

### **Economics and Penalties**

Regularly submitting WindowPoSt is economically rational for storage providers because failing to provide these proofs results in penalties, including loss of their stake and reduced mining power.

***

## Operational Workflow

### **Sector Partitioning**

In Windowed PoSt, a storage provider’s sectors are divided into subsets known as partitions. This division helps manage the proving load by breaking it into smaller, more manageable parts.

### **Proving Windows**

Each partition is assigned a specific time window during which the storage provider must submit proofs. These windows are staggered throughout the day so that not all proofs are due simultaneously, which helps in load balancing on the network and prevents spikes in computational demand.

### **Random Sampling**

Within each window, a random subset of sectors from the partition must be proven. The randomness is crucial for security, ensuring storage providers can't predict which sectors they'll need to prove and thus must maintain all sectors correctly to pass the checks.

### **Fault Tolerance**

The sector is marked as faulty if a storage provider fails to prove a sector (due to data loss or other issues). Storage providers can declare faults proactively to avoid penalties, providing they can recover and continue proving the data in future windows.

### **Submission and Verification**

Proofs are submitted to the blockchain and verified. Successful verification allows the storage provider to continue earning block rewards. Failure to submit valid proofs results in penalties, including loss of block rewards and potential slashing of their stake.
