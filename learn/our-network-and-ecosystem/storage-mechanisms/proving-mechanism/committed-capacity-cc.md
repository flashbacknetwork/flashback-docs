# Committed Capacity (CC)

**Committed Capacity (CC)** refers to a type of sector on the Filecoin network that allows storage providers to commit storage space to the network without having actual storage contract deals to store immediately. These sectors act as placeholders and can be filled with real data later, which helps miners maintain a consistent level of power in the network while waiting for deals. The main benefits of using CC sectors are the ability to earn block rewards in Filecoin and to maintain miner reputation and power without the immediate need to store user data.

## Efficient Use of Committed Capacity

To use Committed Capacity sectors efficiently, storage providers can follow these guidelines:

#### **Deploying CC Sectors Strategically**

Storage providers should deploy CC sectors to maximize their storage capacity and participate in Filecoin's consensus mechanism. Since these sectors still require sealing (a costly and time-consuming process), the decision to use CC sectors should consider the balance between the costs of sealing and the potential block rewards earned.

#### **Upgrading CC Sectors with Real Data**

A significant advantage of CC sectors is the ability to upgrade them with real client data without incurring additional costs for collateral or penalties. This is known as a SnapDeal. This method allows a miner to take an existing CC sector and "snap" a client deal into it, thereby turning it into a regular deal sector.

The Snap Deal process involves updating the sector without resealing it from scratch, which saves on gas fees and sealing time.

#### **Maintaining Active Power and Rewards**

By keeping a certain percentage of storage capacity committed as CC sectors, miners can ensure that they are always participating in the network and can receive block rewards. As real data deals come in, these CC sectors can be gradually replaced with deal sectors.

## Considerations for Efficient CC Sector Usage

* **Cost-Benefit Analysis:** Always weigh the costs of sealing CC sectors against the potential rewards. Consider factors like gas fees, storage deal flow, and market dynamics.
* **Upgrade Strategy:** Have a strategy for upgrading CC sectors to deal sectors based on deal flow. This could mean setting thresholds for when to upgrade or keeping a reserve of CC sectors to quickly onboard new deals.
* **Network Incentives and Penalties:** Be aware of the network’s rules regarding CC sectors, such as collateral requirements and penalties for failing to meet proof deadlines.

***

## **Mixing Real Deals with Fake Deals**

In the Filecoin network, **mixing real deals with fake deals** within the same sector is **impossible**. Filecoin enforces a clear separation between sectors that store client data and sectors that commit capacity to the network without storing actual client data.

### **Deal Sectors and CC Sectors are Distinct**

* Deal sectors are sectors that contain real client data. They require proof that the data is stored correctly and consistently to receive rewards and avoid penalties.
* CC sectors commit storage capacity to the network without storing any actual user data. They earn block rewards by contributing to the network’s power without holding deals initially.

1. **Upgrading CC Sectors with Real Deals:**
   * The upgrade process, known as a **Snap Deal**, allows storage providers to upgrade a CC sector to a deal sector by adding real client data. However, once a CC sector is upgraded to a deal sector, it only contains real deals and does not mix with any "fake deals" or placeholder data.
   * The upgrade must follow specific protocols, including the `ProveReplicaUpdate` steps to ensure that the proof and new data are valid.
2. **Why Mixing is Not Allowed:**
   * Mixing real and fake deals in a single sector would undermine the integrity of the Proof-of-Storage mechanism in Filecoin. Each sector must prove its content consistently to ensure the reliability and trustworthiness of stored data, which is central to Filecoin’s model.
