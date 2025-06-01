---
description: >-
  The reputation system ranks providers based on objective performance metrics
  and community feedback. The system ensures transparency and incentivizes
  providers to maintain high-quality service.
---

# Reputation Scores

The reputation system for **Providers and Consumers** is composed of two primary components:

1. **Objective Score**: Derived from the provider's compliance with SLA requirements specified in the Smart Contract and QoS records **per Data Unit**.
2. **Community Score**: Based on feedback from consumers (services) who have used the provider's services or based on feedback from providers (infrastructure) who serves the consumers.

Each component contributes to the **Reputation Score**, which is used to rank Providers and Consumers in the system and is summarized in the Provider/Consumer's record of the Smart Contract.

***

## :one: Objective Score

The **Objective Score** reflects a provider's adherence to SLAs and performance metrics. It is calculated using data collected from QoS records and SLA compliance checks.&#x20;

Providers and consumers start with a baseline score of **50 points** with a minimum of **0 points** and a maximum of **100 points**.

The first table summarizes the criteria per Data Unit for the Provider and the second table summarizes the criteria per Data Unit for the Consumer.

<table><thead><tr><th width="482.7999267578125">Criteria per Data Unit</th><th>Score</th></tr></thead><tbody><tr><td>Report all SLA requirements on time.</td><td><strong>+1 point</strong></td></tr><tr><td>Meet all SLA requirements and equivalent data between Consumer and Provider.</td><td><strong>+2 points</strong></td></tr><tr><td>Missed report after the reporting window closes.</td><td><strong>-1 point</strong></td></tr><tr><td>Do not meet all SLA requirements or non equivalent data between Consumer and Provider.</td><td><strong>-2 points</strong></td></tr></tbody></table>

**The Objective Score is the mean of daily scores considering all the data units (provided or consumed).**

***

## :two: Community Reputation Score

The **Community Score** reflects consumer and provider satisfaction and trust. It is derived from consumer or provider feedback and ratings.

### :pencil2: Feedback Collection

* Consumers can rate providers on a scale of **1 to 5 stars** after using their services. Respectively, Providers can rate Consumers on a scale of **1 to 5 stars** after using their services.
* Optional comments allow consumers and providers to provide additional context or report specific issues.

### :dart: Scoring Mechanism

* The Community Score is calculated as the **average rating** from all submitted feedback.
* Providers must have at least **10 ratings** for their Community Score to be publicly visible on the platform except if they are verified.&#x20;

### :inbox\_tray: Weighting Feedback

* **Recent Feedback**: Ratings from the last 30 days are weighted more heavily than older ratings.
* **Verified Users**: Feedback from verified Consumers and Providers is weighted more heavily than unverified feedback.

***

## :three: Reputation Score

The overall reputation score is a weighted combination of the Objective and Community Reputation Scores:

Overall Score = (0.7 × Objective Score) + (0.3 × Community Score)

### :notebook\_with\_decorative\_cover: Rationale for Weighting

* The Objective Score has a higher weight (70%) to ensure providers are primarily judged by measurable performance.
* The Community Score (30%) adds a subjective element, reflecting consumers trust and satisfaction.

### :chart\_with\_downwards\_trend: Decay Mechanism

To prevent older performance records from having undue influence, scores decay by **1 point per month** if no new QoS data is recorded **until reaching the score of 50 points**.&#x20;

***

## :8ball: Reporting and Transparency

**Providers** can view their reputation scores in a **dashboard** that includes:

* Objective Score with detailed SLA compliance data.
* Community Score with aggregated feedback and trends.

**Consumers can view a provider's Overall Reputation Score**, along with badges for exceptional performance (e.g., "100% SLA Compliance for 6 Months").

Providers can **dispute inaccurate feedback** or SLA violations through a formal process, which includes re-evaluating QoS records or reviewing consumers complaints.

***

## :top: Incentives for High Reputation

* **Priority Listing**: High-reputation Providers appear at the top of Consumer search results.
* **Performance Bonuses**: Providers with consistently high scores may receive reduced fees or other benefits.
* **Trust Badges**: Visible indicators of reliability (e.g., "Top Performer").

This system ensures a balanced approach to evaluating Providers and Consumers, combining hard metrics with consumer trust to create a fair and transparent ecosystem.
