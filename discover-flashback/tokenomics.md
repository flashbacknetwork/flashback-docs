# 🏦 Tokenomics

The Flashback platform introduces a decentralized economic model that seamlessly connects consumers with sotrage and/or compute providers.&#x20;

Providers are incentivized to maintain high-quality services through performance rewards and penalties for SLA non-compliance.  Consumers will play a key role in the reputation system and Providers in the trust of offering resources.

<mark style="color:red;">**Red**</mark>: Economic flow going out from the user.\
<mark style="color:green;">**Green**</mark>: Economic flow going in the user.\
<mark style="color:purple;">**Purple**</mark>: Economic flow going in or out from the user depending on the scenario.

## :office: Consumers

Here is the breakdown of the different economic flow from the Consumers:

<table><thead><tr><th width="188.99993896484375">Type</th><th width="283.2000732421875">Description</th><th>Value</th></tr></thead><tbody><tr><td><mark style="color:red;"><strong>Unit Payment</strong></mark></td><td>This corresponds to Consumer payments. Depending on the blockchain used, this payment will be blocked in the smart contract.</td><td>Defined by the SLA between Consumer and Provider in FLASH or cryptocurrency agreed with the provider.</td></tr><tr><td><mark style="color:red;"><strong>Unit Standard Fees</strong></mark></td><td>A fee incurs costs for submitting the payment in the smart contract and for making the daily payment for the period indicated.</td><td>Cryptocurrency of the smart contract. Minimum depends on the chain.</td></tr><tr><td><mark style="color:purple;"><strong>Unit Quality Collateral</strong></mark></td><td>A collateral that is used for the transaction operations. 50% of the remaining is returned if the unit's reputation score is above 50. The remaining is burnt.</td><td>0.5% of the Unit Payment.</td></tr><tr><td><mark style="color:red;"><strong>Platform Operational Fees</strong></mark></td><td>Running costs to sustain Flashback’s operations, such as the marketplace and other advantages related to Flashback DePin.</td><td>5% of Unit Payment. <br>1% if paid in FLASH.</td></tr><tr><td><mark style="color:purple;"><strong>Staking Collateral</strong></mark></td><td>Lock system of FLASH to be able to interact with the platform.</td><td>A minimum of 10 USD with 30-day <a href="https://help.coinbase.com/en/prime/staking/unbonding">unbonding period</a> for unstaking.<br>Supported cryptocurrency of smart contracts or FLASH.</td></tr><tr><td><mark style="color:green;"><strong>Reputation Reward</strong></mark></td><td>A daily reward based on their Reputation Score.</td><td>Score from 60 to 79:<br>+1% APY of Token Allocation<br>Score +80:<br>+3% APY of Token Allocation</td></tr><tr><td><mark style="color:red;"><strong>Reputation Slashing</strong></mark></td><td>A daily penalty based on their Reputation Score.</td><td>Score from 20 to 39:<br>-1% APY of Token Allocation<br>Score -19:<br>-3% APY of Token Allocation</td></tr></tbody></table>

## :robot: Providers

Here is the breakdown of the different economic flow from the Providers:

<table><thead><tr><th width="188.99993896484375">Type</th><th width="283.2000732421875">Description</th><th>Value</th></tr></thead><tbody><tr><td><mark style="color:red;"><strong>Unit Deal Submission Fees</strong></mark></td><td>Deal submission fee paid only if Comsumer accepts the unit's SLA submitted by the Consumer.</td><td>0.5% of Unit Payment.<br>0.1% of Unit Payment if FLASH.<br>Proposed unit payment must be above 50 USD.</td></tr><tr><td><mark style="color:red;"><strong>Unit Priority Fees</strong></mark></td><td>It is an additional fee the Provider may pay to be selected by providers in priority.</td><td>Minimum of 0.01 USD.</td></tr><tr><td><mark style="color:green;"><strong>Unit SLA Bonus</strong></mark></td><td>The unit reaches a reputation score above 80.</td><td>back 90% of the remaining of your unit quality collateral.</td></tr><tr><td><mark style="color:red;"><strong>Unit Slashing</strong></mark></td><td>Burnt unit payment if the Provider does not meet the SLA.</td><td>10% of the Unit Payment.</td></tr><tr><td><mark style="color:purple;"><strong>Staking Collateral</strong></mark></td><td>Lock system of FLASH to be able to interact with the platform.</td><td>A minimum of 1,000 USD with 30-day <a href="https://help.coinbase.com/en/prime/staking/unbonding">unbonding period</a> for unstaking.<br>Supported cryptocurrency of smart contracts or FLASH.</td></tr><tr><td><mark style="color:green;"><strong>Reputation Reward</strong></mark></td><td>A daily reward based on their Reputation Score.</td><td>Score from 60 to 79:<br>+5% APY of Token Allocation<br>Score +80:<br>+12% APY of Token Allocation</td></tr><tr><td><mark style="color:red;"><strong>Reputation Slashing</strong></mark></td><td>A daily penalty based on their Reputation Score.</td><td>Score from 20 to 39:<br>-5% APY of Token Allocation<br>Score -19:<br>-12% APY of Token Allocation</td></tr><tr><td><mark style="color:green;"><strong>Storage Resource Reward</strong></mark></td><td>A reward dedicated to the data storage resources allocated through its node.</td><td>XYZ is the resource in TB.<br><br>If +1 TB: <br>+0.0005%*XYZ APY of Token Allocation<br>If +1,000 TB:<br>+0.001%*XYZ APY of Token Allocation<br><br>Max.: 12% APY of Token Allocation</td></tr></tbody></table>

***

## :coin: **FLASH Token**

The FLASH token will serve as the backbone of the Flashback ecosystem, facilitating The FLASH token is the foundation of the Flashback ecosystem, facilitating transactions, incentives, and governance. Here is a high-level overview of the token flow through the ecosystem:

**1. Consumer Payments**

* Consumers acquire FLASH tokens via exchanges or directly on the platform using fiat or other cryptocurrencies.
* FLASH is used to pay for storage services, unlocking discounts and additional features.

**2. Provider Incentives**

* Providers earn FLASH through performance rewards, staking incentives, and SLA bonuses.
* Providers can stake FLASH to participate in governance or convert it into fiat/native tokens to cover operational expenses.

**3. Platform Operations**

* Flashback collects a small transaction fee for managing payments and services, ensuring a sustainable revenue stream.
* A portion of these fees is redistributed to token holders or reinvested in platform development and community growth.

**4. Governance and Community Engagement**

* FLASH token holders participate in platform governance, voting on feature updates, policy changes, and fund allocations.
* Community members contribute to open-source projects, documentation, or marketing efforts and earn FLASH tokens as rewards.

***

## :zap:Extension to Flashback Platform

To align the existing tier-based and transaction-fee business model with the FLASH token, we can layer in token-centric incentives, discounts, and governance mechanisms. Below is a proposal for how FLASH could be integrated at each stage of revenue and cost flows.

### :books:Tier-Based Subscriptions with FLASH Integration

We will allow customers to pay in FLASH tokens and "lock in” a 20% discount by prepaying for their tier in FLASH tokens instead of fiat.

If the user is a consumer of the Flashback DePin platform (having a staking collateral):

* Users can get tiers access for one year by adding FLASH tokens worth at least three times the annual plan cost in its staking collateral. As long as the tokens remain staked, they keep Pro Tier; if they withdraw them, they revert to their previous tier at the next billing cycle.\
  Example: _The user of Flashback DePin is a consumer with a staking collateral of 100 FLASH. He is adding 300 FLASH in the collateral that corresponds to 3x the annual costs of Pro Tier. He receives 1 year free to his Flashback Platform account._
* At the time of tier billing, we convert 1% of your payment back into FLASH for loyalty.
* Because FLASH can be liquid and subject to market fluctuations, you can peg the FLASH-price of each plan to a moving 7-day average of the USD/FLASH rate. That way, consumers see a roughly stable FLASH price and avoid sudden token volatility.
* Pay any add-ons in the paid tiers in FLASH with a discount of 20%.

### :sparkler: “Data-Traffic Allowance” Overage with FLASH Integration

If a consumer opts to pay overage in FLASH, they receive a sliding-scale discount:

* 2% discount if they pay overage up to 1,000 GB in FLASH.
* 5% discount for 1 TB – 100 TB in FLASH.
* 10% discount for > 100 TB overage in FLASH.

***

## :ballot\_box: Utility & Governance Synergies

#### 4.1. Governance Participation & Voting Weight

* **FLASH-Weighted Voting:**\
  • On protocol governance proposals (e.g., changing overage rates, adding new providers, adjusting weighting in the reputation formula), each holder’s vote is weighted by their staked FLASH amount.\
  • To prevent concentration, introduce a quadratic-voting option for major changes: cost in FLASH ∝ (votes)², tempering whale dominance.
* **Locked vs. Liquid Voting:**\
  • Users who lock FLASH for 6–12 months earn “Voting Boosters” (×1.5 weight) but cannot unstake until their lock period ends. This encourages long-term alignment.

#### 4.2. Community-Reward Pool & Bounties

* **Continuous Liquidity Mining for QoS Reporters:**\
  • Dedicate a percentage of slashed tokens and transaction fees into a “Reporter Reward Pool.”\
  • Consumers (and providers) who submit high-quality, timestamped, and verified QoS/SLA measurements can claim a small FLASH reward from this pool.\
  • Helps seed early telemetry, builds trust in measurement integrity, and distributes tokens to active participants.
* **Development Bounties & Open-Source Contributions:**\
  • Fund flashback-related community efforts (e.g., writing SDKs, building monitoring dashboards) using a portion of staked tokens. Contributors receive FLASH for accepted PRs, documentation efforts, or bug fixes.

By weaving FLASH into both the tiered subscription logic and the per-GB transaction fees, Flashback can turn token usage into a core lever for both revenue optimization and network effects—driving consistent token demand, rewarding honest behavior, and fostering long-term alignment between consumers, providers, and the platform itself.



