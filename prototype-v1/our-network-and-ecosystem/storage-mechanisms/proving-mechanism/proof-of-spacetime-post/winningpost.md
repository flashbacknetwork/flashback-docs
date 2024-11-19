# WinningPoSt

Winning Proof of Spacetime (WinningPoSt) is another key implementation of the Proof of Spacetime used in the Filecoin network, specifically designed to incentivize storage providers by allowing them to win block rewards through cryptographic challenges.

***

## General Concept introduction

### **Purpose**

WinningPoSt is a mechanism for proving that a storage provider maintains a replica of the data at a specific time when selected to create a new block. Unlike WindowPoSt, a periodic check of all stored data, WinningPoSt occurs only when a miner is elected through the network’s Expected Consensus algorithm to mine a new block.

### **Process**

When a storage provider is selected to create a new block, it must generate a proof (WinningPoSt) to demonstrate that it is genuinely storing the client data it has committed to. This proof must be submitted within the current epoch (a short, fixed period in the Filecoin blockchain), and failure to submit results in losing the chance to mine that block.

### Structure

The WinningPoSt proof process involves a random selection of sectors for which the miner must provide proof of storage. This randomness ensures that the storage provider consistently maintains its entire set of sectors.

### **Economics and Rewards**

Successfully submitting a WinningPoSt proof earns the miner block rewards and transaction fees. There are no penalties for failing to submit a WinningPoSt proof on time, but the opportunity to earn that block's rewards is lost.

***

## Operational Workflow

### **Leader Election**

At the beginning of each epoch, Filecoin’s Expected Consensus algorithm randomly selects a few storage providers as leaders eligible to propose new blocks. This selection is based on the storage provider’s Quality Adjusted Power (QAP) in the network, meaning that providers storing more and verified data have higher chances of being selected.

### **Proof Generation**

Once elected, the selected storage provider must generate a WinningPoSt proof. This proof involves selecting a random subset of its committed sectors and proving that it still has the data. This proof must be submitted within the same epoch the provider selected, emphasizing speed and efficiency.

### **Random Sampling**

The network performs a cryptographic challenge that requires the selected storage provider to prove it is maintaining a randomly chosen set of sectors. This randomness prevents providers from cheating or selectively maintaining only specific sectors.

### **Proof Submission and Validation**

The WinningPoSt proof and the block proposal for the blockchain network have been submitted. The proof is then validated by other nodes in the network. If the proof is valid, the provider earns block rewards and network transaction fees associated with the proposed block.

### **Incentives and Non-Penalization for Missed Opportunities**

There is no direct penalty for a storage provider that fails to submit a WinningPoSt on time; however, it misses out on the potential block reward and transaction fees for that epoch. This mechanism encourages storage providers to maintain high uptime and reliability to maximize their chances of earning rewards.
