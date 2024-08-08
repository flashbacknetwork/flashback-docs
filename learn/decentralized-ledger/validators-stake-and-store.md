---
author: Brieuc Berruet <brieuc.berruet@thenephelecloud.com>
---

# Validators: Stake first, Store after

The proof-of-stake spacetime (PoS-ST) has different responsibilities as validators. Validators are primarily staking-based, equivalent to Ethereum's validators, which are [full nodes](../our-network-and-ecosystem/ethereum-stack-in-nephele/basics/nodes-and-clients-1.md). A validator stores data, processes transactions, and adds new blocks to the blockchain. However, storage duties are limited to on-chain data storage.

The validators can decide to be storage providers by enabling the proof-of-spacetime (PoSt) commitments as validators. This way, you extend your duties with off-chain file storage, the cornerstone of our DePIN-based cloud storage.

## Why be a validator?

### Earn rewards and Be Profitable

Rewards are given for activities that help keep the network secure and running smoothly. You'll earn staking rewards for running Nephele software that groups transactions into new blocks and verifies the work of others. This is essential for maintaining the integrity and security of the chain.

A validator can decide to participate in the file storage duties by allowing the commitment of storage proofs. After setting your parameters and operating fees (what people must pay to store files in your validator), you'll earn rewards according to your performances assessed by the [quality-of-network (QoN) optimizer](quality-of-network-qon-optimizer.md). You will participate in the diversity of storage offers and be a founder of the mass adoption of innovative use cases in the web3 ecosystem. With our novel [proof](consensus-proof-of-stake-spacetime.md), you can also parametrize as you want the storage duties and how you want to commit them to the network. This unique flexibility will allow you to develop a business model with your storage and be competitive. You'll have the best profitability of your storage space.

### Secure the network and Improve the Privacy

As more NEPH is staked, the network becomes more secure against attacks. This is because controlling most of the network would require owning the most staked NEPH. Essentially, the more NEPH staked, the harder it is for anyone to gain enough control to pose a threat. You will be a cornerstone of the security and decentralization of the network.

If you enable file storage, you can participate in the cloud storage layer and improve the network's security, privacy, and value. You will be the precursor of a fairer and competitive world where every individual and business can store their files according to their requirements.

### Participate in a Sustainable Ecosystem

Doing staking is the best way to consume limited resources, the opposite of the proof-of-work or proof-of-capacity-based systems. This is why Nephele used the staking model to avoid a frantic race for the power of block validation.

Nephele chose to develop a sustainable ecosystem by design. You'll be part of decision processes toward greener and more sustainable cloud storage by offering and optimizing our operating fees depending on your energy consumption, workforce, and other criteria.

***

## 3 Ways to be a staking Validator

There are 3 different ways to become a validator:

### **Solo Validator**

This is the ultimate standard. You have full participation rewards, improve the decentralization of the network, and never need to trust anyone else with your funds. You'll need a dedicated computer connected to the Internet. This connection must be stable and available \~24/7.

### Staking-as-a-Service

* **Your 10,000 FLASH**: Start with your stake.
* **Your Validator Keys**: Manage your credentials.
* **Entrusted Node Operation**: Leave the technicalities to the experts.

If you're hesitant about managing hardware but still want to stake your 10,000 FLASH, consider using staking-as-a-service. This option guides you through creating validator credentials, uploading your signing keys, and depositing your 10,000 FLASH. The service handles validation on your behalf, allowing you to earn native block rewards.

This method requires trusting the service provider. To mitigate risk, withdrawal keys—allowing you to reclaim your FLASH—are typically retained by you, ensuring security and control.

### Pooled Staking

* **Stake Any Amount**: Flexible entry.
* **Earn Rewards**: Participate in gains.
* **Keep it Simple**: User-friendly approach.
* **Popular Choice**: Widely used option.

Pooled staking offers a viable alternative for those who need more time to be ready or able to stake 10,000 FLASH directly. Many services offer what's known as 'liquid staking', which issues an ERC-20 liquidity token that represents your staked FLASH. This makes it easy to enter or exit staking positions just like a token swap and allows you to maintain custody of your assets in your own Flashback wallet.

Remember, third parties develop pooled staking solutions and are not native to the Flashback network. These platforms introduce their own set of risks.

Both staking methods provide ways to engage with the Flashback ecosystem, whether you prefer a hands-on approach or seek pooled options' simplicity and lower entry requirements.

You can find more details on how to [become a validator (WIP)](../../participate/become-a-validator.md).

***

## The storage duties <a href="#why-should-i-run-an-ethereum-node" id="why-should-i-run-an-ethereum-node"></a>

Becoming a storage provider on the Flashback network involves several steps, from setting up the necessary hardware to participating actively in the network’s operations. We recommend you to read everything about the [storage proving](../our-network-and-ecosystem/storage-mechanisms/proving-mechanism/) and [differences with Filecoin](../our-network-and-ecosystem/storage-mechanisms/differences-with-flashback.md). Here’s a detailed guide on how you can become a storage provider in Flashback:

### 1. Have a nice **hardware setup**

To begin, you'll need to invest in appropriate hardware. Flashback doesn't require specialized ASIC hardware but does need robust computational resources:

* **High-Performance CPUs**: These are used to efficiently handle the computational demands of sealing and PoSt processes.
* **Substantial RAM**: To support the intensive operations during the sealing process.
* **Fast and Reliable Storage**: Preferably solid-state drives (SSD) to quickly access and process large volumes of data.
* **High-Capacity Hard Drives**: For the long-term storage of sealed data.

### 2. **Committing Storage to the Network**

* **Sealing Data**: The process begins with sealing data, which involves preparing your storage to comply with proof protocols.
* **Sector Pledging**: Each piece of data stored on Flashback is contained in a sector. It would be best if you pledged these sectors to the network, indicating you are committing space to store data.

### 3. **Participate in the Storage Market**

* **Bid on Deals**: Storage providers can browse the storage market for client deals. Deals specify the amount of data, storage duration, and price.
* **Seal and Prove Stored Data**: After accepting a deal, you will seal the client's data into a sector and continuously prove you are storing it through the Proof-of-Spacetime mechanism.

### 4. **Maintain and Optimize Operations**

* **Regularly Submit Proofs**: You must submit regular proofs to verify that you are storing the data correctly.
* **Monitor and Upgrade**: Continuously monitor your operations and hardware, and make necessary upgrades or fixes to ensure optimal performance and compliance with Flashback’s evolving protocols.

### 5. **Comply with Network Upgrades and Community Standards**

* **Stay Updated**: Keep your software up-to-date with the latest releases from Flashback. This includes updates that may affect consensus, storage proofs, and the storage market dynamics.
* **Engage with the Community**: Participating in the Flashback community can provide support, insights, and essential updates regarding protocol changes.

You can find more details on how to [become a validator (WIP)](../../participate/become-a-validator.md).
