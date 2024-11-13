# Storage providers' Collateral

## Initial Pledge Collateral

* **Purpose and Composition**: The initial pledge collateral is a security deposit that storage providers must pay when sealing a new sector, composed of a storage pledge and a [consensus pledge](https://spec.filecoin.io/systems/filecoin\_blockchain/storage\_power\_consensus/). This collateral is designed to incentivize storage providers to fulfill their storage obligations and to secure the network by deterring malicious or unreliable behavior.
* **Amount and Calculation**: The amount is calculated based on the expected block rewards the sector will earn over approximately 20 days, ensuring the pledge is large enough to cover potential faults and penalties but feasible for new storage providers.
* **Dynamic Adjustments**: The consensus pledge part of the initial pledge is adjusted based on the sector's contribution to the network's total quality-adjusted power (QAP) and the circulating supply of FIL tokens, aiming to lock about 30% of the circulating supply in pledges.

## Block Reward Collateral

* **Incentive Alignment**: Block rewards earned by a sector also serve as collateral, which can be slashed if the miner fails to fulfill the storage deal or terminates a sector prematurely. This mechanism ensures storage providers have continuous financial incentives to maintain reliable storage.
* **Vesting Schedule**: Rewards are vested over a fixed duration, providing storage providers with liquidity for ongoing operations while retaining a strong incentive to preserve data until the end of the deal. This system balances the need for immediate liquidity against the risk of premature sector termination.
* **Economic Impact**: Using block rewards as collateral allows for a lower initial cash outlay from storage providers, reducing barriers to entry while still providing a robust mechanism to enforce deal terms and network reliability.

## Storage Deal Collateral

* **Deal-Specific Security**: Storage providers provide this collateral to guarantee individual storage deals, ensuring they have a vested interest in maintaining the data integrity and availability agreed upon in the storage deal contracts.
* **Market Dynamics**: This form of collateral allows storage providers to differentiate themselves in the market, potentially attracting more clients by demonstrating higher reliability or offering better terms.
* **Regulatory Mechanism**: Governed by the Storage Market Actor, this collateral aligns the incentives of storage providers with their clients, ensuring that penalties are applied for non-compliance with the agreed terms of storage contracts.

These collateral mechanisms collectively help maintain the reliability, security, and economic viability of the Filecoin network by aligning miner incentives with network and client needs.
