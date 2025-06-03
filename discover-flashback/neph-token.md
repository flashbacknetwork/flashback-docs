# 🏦 Economy Model

The Flashback platform introduces a decentralized economic model that seamlessly connects consumers with sotrage and/or compute providers.&#x20;

Providers are incentivized to maintain high-quality services through performance rewards and penalties for SLA non-compliance.  Consumers will play a key role in the reputation system and Providers in the trust of offering resources.

<mark style="color:red;">**Red**</mark>: Economic flow going out from the user.\
<mark style="color:green;">**Green**</mark>: Economic flow going in the user.\
<mark style="color:blue;">**Blue**</mark>: Economic flow going in or out from the user depending on the scenario.

## :office: Consumers

Here is the breakdown of the different economic flow from the Consumers:

<table><thead><tr><th width="188.99993896484375">Type</th><th width="283.2000732421875">Description</th><th>Value</th></tr></thead><tbody><tr><td><mark style="color:red;"><strong>Unit Deal Submission</strong></mark></td><td>Deal submission fee paid only if Provider accepts the unit's SLA submitted by the Consumer.</td><td>0.5% of Unit Payment.<br>0.1% of Unit Payment if FLASH.</td></tr><tr><td><mark style="color:red;"><strong>Unit Payment</strong></mark></td><td>This corresponds to consumer payments. Depending on the blockchain used, this payment will be blocked in the smart contract.</td><td>Defined by the SLA between Consumer and Provider.</td></tr><tr><td><mark style="color:red;"><strong>Unit Fees</strong></mark></td><td>A fee incurs costs for submitting the payment in the smart contract and for making the daily payment for the period indicated.</td><td>Depend on the network. Included in Platform Operational Fees.</td></tr><tr><td><mark style="color:purple;"><strong>Unit Quality Collateral</strong></mark></td><td>A collateral that is used for the transaction operations. 50% of the remaining is returned if the unit's reputation score is above 50.</td><td>0.5% of the Unit Payment.</td></tr><tr><td><mark style="color:red;"><strong>Platform Operational Fees</strong></mark></td><td>Running costs to sustain Flashback’s operations, such as the marketplace and other advantages related to Flashback DePin.</td><td>5% of Unit Payment. <br>1% if paid in FLASH.</td></tr><tr><td><mark style="color:purple;"><strong>Staking Collateral</strong></mark></td><td>Lock system of FLASH to be able to interact with the platform.</td><td>A minimum of 100 FLASH with 30-day <a href="https://help.coinbase.com/en/prime/staking/unbonding">unbonding period</a> for unstaking.</td></tr><tr><td><mark style="color:green;"><strong>Reputation Reward</strong></mark></td><td>A daily reward based on their Reputation Score.</td><td>Score from 60 to 79:<br>+1% APY of Token Allocation<br>Score +80:<br>+3% APY of Token Allocation</td></tr><tr><td><mark style="color:red;"><strong>Reputation Slashing</strong></mark></td><td>A daily penalty based on their Reputation Score.</td><td>Score from 20 to 39:<br>-1% APY of Token Allocation<br>Score -19:<br>-3% APY of Token Allocation</td></tr></tbody></table>

## :factory: Providers

Here is the breakdown of the different economic flow from the Providers:

<table><thead><tr><th width="188.99993896484375">Type</th><th width="283.2000732421875">Description</th><th>Value</th></tr></thead><tbody><tr><td><mark style="color:red;"><strong>Unit Deal Submission</strong></mark></td><td>Deal submission fee paid only if Comsumer accepts the unit's SLA submitted by the Consumer.</td><td>0.5% of Unit Payment.<br>0.1% of Unit Payment if FLASH.</td></tr><tr><td><mark style="color:purple;"><strong>Unit Quality Collateral</strong></mark></td><td>A collateral that is used for the transaction operations. 50% of the remaining is returned if the unit's reputation score is above 50.</td><td>0.5% of the Unit Payment.</td></tr><tr><td><mark style="color:green;"><strong>Unit SLA Bonus</strong></mark></td><td>The unit reaches a reputation score above 80.</td><td>back 90% of the remaining of your unit quality collateral.</td></tr><tr><td><mark style="color:purple;"><strong>Staking Collateral</strong></mark></td><td>Lock system of FLASH to be able to interact with the platform.</td><td>A minimum of 10,000 FLASH with 30-day <a href="https://help.coinbase.com/en/prime/staking/unbonding">unbonding period</a> for unstaking.</td></tr><tr><td><mark style="color:green;"><strong>Reputation Reward</strong></mark></td><td>A daily reward based on their Reputation Score.</td><td>Score from 60 to 79:<br>+5% APY of Token Allocation<br>Score +80:<br>+12% APY of Token Allocation</td></tr><tr><td><mark style="color:red;"><strong>Reputation Slashing</strong></mark></td><td>A daily penalty based on their Reputation Score.</td><td>Score from 20 to 39:<br>-5% APY of Token Allocation<br>Score -19:<br>-12% APY of Token Allocation</td></tr><tr><td><mark style="color:green;"><strong>Storage Resource Reward</strong></mark></td><td>A reward dedicated to the data storage resources allocated through its node.</td><td>XYZ is the resource in TB.<br><br>If +1 TB: <br>+0.0005%*XYZ APY of Token Allocation<br>If +1,000 TB:<br>+0.001%*XYZ APY of Token Allocation<br><br>Max.: 12% APY of Token Allocation</td></tr></tbody></table>

***

## :pizza: **FLASH Token**

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

#### Token-Discounted Tiers

* We will allow customers to pay in FLASH tokens and "lock in” a 20% discount by prepaying for their tier in FLASH tokens instead of fiat.
* If the user is a consumer of the Flashback DePin platform:
  * Users can get Pro Tier access for one year by adding FLASH tokens worth at least three times the annual plan cost in its staking collateral. As long as the tokens remain staked, they keep Pro Tier; if they withdraw them, they revert to their previous tier at the next billing cycle.\
    Example: The user is a consumer with a staking collateral of 100 FLASH. He is adding 300 FLASH in the collateral that corresponds to&#x20;
* At the time of tier billing, the platform converts 5% of your payment back into FLASH” for loyalty. if a user pays $100 in USD, then $95 goes to the tier fee and $5 converts to FLASH and is automatically staked or credited to their wallet.

#### 1.2. Token-Only Tiers (Premium “FLASH-Native” Plans)

* **Special All-In-FLASH Plans:**\
  • Create one or two premium plans (e.g., “Platinum”) that can only be purchased with FLASH at a discounted rate (e.g., 30 % below the USD equivalent).\
  • These FLASH-only tiers could bundle additional perks:
  * Waived overage fees (see Section 2) up to a certain threshold.
  * Early access to new features (e.g., beta access to Compute-on-Demand).
  * Governance voting weight multipliers (see Section 4).
* **Dynamic Pricing in FLASH:**\
  • Because FLASH is liquid and subject to market fluctuations, peg the FLASH-price of each plan to a moving 7-day average of the USD/FLASH rate. That way, consumers see a roughly stable FLASH price and avoid sudden token volatility.

***

### 2. Transaction Fees (“Data-Traffic Allowance” Overage) + FLASH

#### 2.1. Paying Overage in FLASH for Discounts

* **Standard Overage Fees in USD:**\
  • Currently, once a user exceeds their monthly allotment (e.g., 2 TB), they pay $0.02/GB extra in USD.
* **FLASH-Owed Volume Discount:**\
  • If a consumer opts to pay overage in FLASH, they receive a sliding-scale discount:
  * 5 % discount if they pay overage up to 100 GB in FLASH.
  * 10 % discount for 100 GB–500 GB in FLASH.
  * 15 % discount for > 500 GB overage in FLASH.\
    • This encourages heavier users to hold and spend FLASH, creating consistent token demand.
* **Surge Pricing Floor via Token Burn:**\
  • During network congestion (e.g., periods when on-demand compute is in high demand), impose a small “surge burn” on top of the usual fee if paid in USD. But if paid in FLASH, the surge “fee” is burned instead of being captured by the protocol, ensuring scarcity.
  * Example: Normal USD overage = $0.02/GB. Surge period = +50 % = $0.03/GB (USD). If user pays in FLASH during surge, they burn 0.025 FLASH/GB (with 0.005 FLASH/GB permanently burned, 0.020 FLASH/GB distributed to providers).

#### 2.2. Tier-Bundled FLASH Credits

* **Monthly FLASH Credit Allocation:**\
  • Each tier comes with a small monthly “FLASH credit.” For instance:
  * Bronze (2 TB) → 10 FLASH credits/month (worth equivalent of $1–$2).
  * Silver (5 TB) → 30 FLASH credits/month.
  * Gold (10 TB) → 75 FLASH credits/month.\
    • Credits can be applied toward transaction fees (overages) or in-platform purchases (e.g., “priority queue” for compute). Unused credits roll over for up to 3 months.
* **Credit Bonus for On-Chain Commitment:**\
  • If a user stakes FLASH for a 3-month commitment, they receive doubled FLASH credits (e.g., Bronze user now gets 20 credits/month). This both locks up token supply and reduces churn.

#### 2.3. Settlement Flexibility via FLASH Escrow

* **Escrow-Style Prepayment:**\
  • Allow users to deposit a pool of FLASH into the contract (on Soroban). Each day, the contract automatically deducts the equivalent transaction-fee in FLASH (based on a formula that references Oracle-fed USD/FLASH price).\
  • This “auto-pay” mechanism prevents interruption; customers aren’t required to manually top up daily. It also reduces gas/friction by batching multiple days if they have surplus.

***

### 3. Provider-Side Incentives & Revenue Flows

#### 3.1. Earning in FLASH vs. USD

* **Providers Paid Primarily in FLASH:**\
  • By default, providers receive a large portion (e.g., 90 %) of their performance rewards (bandwidth, storage, compute) in FLASH tokens. They can convert tokens to USD on secondary markets or hold to capture governance weight.\
  • Providers opting to receive a majority in USD pay a small conversion fee (1–2 % of revenue) back to the protocol, which is burned or redistributed to token stakers.
* **Staking to Become “Preferred Provider”:**\
  • Require a minimum stake of FLASH (e.g., 5,000 FLASH bonded for 60 days) to be eligible for “preferred” search placement when matching consumers to providers.\
  • This stake can be slashed (partial penalty) if SLA compliance falls below thresholds for 7 consecutive days.

#### 3.2. Token-Burned Penalties for SLA Non-Compliance

* **Automatic Slashing Mechanism:**\
  • If a provider misses an SLA (e.g., 99.5 % uptime requirement), the smart contract automatically slashes a small percentage of their staked FLASH (e.g., 1 % per critical SLA breach) up to a maximum of 10 % slash per billing cycle.\
  • Slashed tokens are sent to a “Community Reward Pool” used to reward consumers who report accurate QoS data (see Section 4).
* **Tiered Performance Bonuses:**\
  • Providers whose monthly Objective Reputation Score is ≥ 95 (i.e., few to no SLA misses) receive a bonus paid in FLASH from the “Performance Rewards Pool” (sourced from a fraction of all transaction fees).

***

### 4. Utility & Governance Synergies

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

***

### 5. Summary of FLASH-Enabled Economic Flows

1. **Consumers → Platform (Red Flows):**
   * **Tier Subscription:** USD or FLASH (discounted).
   * **Transaction/Overage Fee:** USD (standard) or FLASH (discounted + potential burn portion).
   * **Staking for Upgrades:** Lock FLASH to get higher tiers or additional credits.
   * **Governance Fee (Optional):** Small FLASH burn for submitting community proposals.
2. **Platform → Consumers (Green/Blue Flows):**
   * **Monthly FLASH Credits:** Allocated per tier, usable toward next month’s fees.
   * **Reporter Rewards:** FLASH rewarded for high-quality QoS submissions or bug bounties.
   * **Governance Incentives:** Voting weight multipliers for locked FLASH.
3. **Platform → Providers (Green Flows):**
   * **Performance Rewards:** FLASH payouts for meeting/exceeding SLAs.
   * **Staking Incentives:** Earn additional FLASH yield by bonding tokens to the protocol.
4. **Providers → Platform (Red Flows):**
   * **Slashing Penalties:** FLASH slashed for SLA breaches or unverified measurements.
   * **Platform Fees (small):** If providers opt for USD, they pay conversion fees back in FLASH to the protocol.
5. **Platform Operations (Blue Flows):**
   * **Fee Collection & Redistribution:** Portion of transaction fees (in FLASH or USD) goes to platform dev fund, staked token buybacks, and community reward pools.
   * **Token Burn & Sink:**
     * Burn a fraction of every overage-fee paid in FLASH (e.g., 1 %), shrinking circulating supply.
     * Burn penalties from SLA breaches.

***

#### Benefits of This Integration

* **Stronger Token Utility:** By giving users (both consumers and providers) tangible discounts and staking benefits, FLASH demand increases naturally.
* **Alignment of Incentives:** Providers have “skin in the game” via staking, while consumers contribute high-integrity data in exchange for token rewards.
* **Reduced Churn & Increased Stickiness:** Staking for tier upgrades and monthly credit rollovers creates an incentive to keep tokens locked and engaged.
* **Sustainable Tokenomics:** Burns from penalties and small transaction fees remove tokens from circulation, offsetting new minting or rewards, which stabilizes token value.
* **Community-Driven Growth:** Bounties, reporter rewards, and governance fosters open-source contributions, building a stronger ecosystem around Flashback.

By weaving FLASH into both the tiered subscription logic and the per-GB transaction fees, Flashback can turn token usage into a core lever for both revenue optimization and network effects—driving consistent token demand, rewarding honest behavior, and fostering long-term alignment between consumers, providers, and the platform itself.



