---
description: >-
  The reputation system ranks providers based on objective performance metrics.
  The system ensures transparency and incentivizes providers to maintain
  high-quality service.
---

# Reputation Scores

## Reputation Score

The **Reputation Score** reflects a provider's adherence to SLAs and performance metrics. It is calculated using data collected from QoS records and SLA compliance checks.&#x20;

Providers start with a baseline score of **50 points** with a minimum of **0 points** and a maximum of **100 points**.

The table summarizes the criteria per Data Unit for the Provider.

<table><thead><tr><th width="482.7999267578125">Criteria per Data Unit</th><th>Score</th></tr></thead><tbody><tr><td>Report all SLA requirements on time.</td><td><strong>+1 point</strong></td></tr><tr><td>Meet all SLA requirements.</td><td><strong>+2 points</strong></td></tr><tr><td>Performances above 20% of the SLA requirements.</td><td><strong>+3 points</strong></td></tr><tr><td>Missed report after the reporting window closes.</td><td><strong>-1 point</strong></td></tr><tr><td>Do not meet all SLA requirements.</td><td><strong>-2 points</strong></td></tr><tr><td>Performances bellow 20% of the SLA requirements.</td><td><strong>-3 points</strong></td></tr></tbody></table>

**The Reputation Score is the mean of daily scores considering all the data units**

### :chart\_with\_downwards\_trend: Decay Mechanism

To prevent older performance records from having undue influence, scores decay by **10 point per month** if no new QoS data is recorded **until reaching the score of 50 points**.&#x20;

***

## :8ball: Reporting and Transparency

**Providers** can view their reputation scores in a **dashboard** that includes:

* Objective Score with detailed SLA compliance data.
* Community Notes with aggregated feedback and trends.

**Consumers can view a provider's Overall Reputation Score**, along with badges for exceptional performance (e.g., "100% SLA Compliance for 6 Months").

***

## :top: Incentives for High Reputation

* **Priority Listing**: High-reputation Providers appear at the top of Consumer search results.
* **Trust Badges**: Visible indicators of reliability (e.g., "Top Performer").

This system ensures a balanced approach to evaluating Providers and Consumers, combining hard metrics with consumer trust to create a fair and transparent ecosystem.
