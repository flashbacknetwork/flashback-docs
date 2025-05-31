---
description: >-
  The reputation system ranks providers based on objective performance metrics
  and community feedback. The system ensures transparency and incentivizes
  providers to maintain high-quality service.
---

# Reputation system

## Reputation System Overview

The reputation system is composed of two primary components:

1. **Objective Reputation Score**: Derived from the provider's compliance with SLA requirements specified in the Smart Contract and QoS records.
2. **Community Reputation Score**: Based on feedback from consumers (services) who have used the provider's services.

Each component contributes to the overall reputation score, which is used to rank providers in the system and is summarized in the Provider's record of the Smart Contract.

### 1. Objective Reputation Score

The **Objective Reputation Score** reflects a provider's adherence to SLAs and performance metrics. It is calculated using data collected from QoS records and SLA compliance checks.

#### Scoring Mechanism

* Providers start with a baseline score of **50 points**.
* **Positive Adjustments**:
  * **+1 point** for each day the provider meets all SLA requirements.
  * **+2 points** for exceptional performance (e.g., exceeding SLA benchmarks by 20% or more).
* **Negative Adjustments**:
  * **-1 point** for each day the provider fails to meet any SLA requirement.
  * **-2 points** for critical failures (e.g., downtime exceeding 1 hour in a 24-hour period).

#### Floor and Ceiling

* The score has a minimum of **0 points** and a maximum of **100 points**.

#### Decay Mechanism

* To prevent older performance records from having undue influence, scores decay by **1 point per month** if no new QoS data is recorded.

### 2. Community Reputation Score

The **Community Reputation Score** reflects consumer satisfaction and trust. It is derived from consumer feedback and ratings.

#### Feedback Collection

* Consumers can rate providers on a scale of **1 to 5 stars** after using their services.
* Optional comments allow consumers to provide additional context or report specific issues.

#### Scoring Mechanism

* The Community Reputation Score is calculated as the **average rating** from all submitted feedback.
* Providers must have at least **10 ratings** for their Community Reputation Score to be publicly visible.

#### Weighting Feedback

* **Recent Feedback**: Ratings from the last 30 days are weighted more heavily than older ratings.
* **Verified Consumers**: Feedback from verified consumers (services) is weighted more heavily than unverified feedback.

### 3. Combined Reputation Score

The overall reputation score is a weighted combination of the Objective and Community Reputation Scores:

Overall Score = (0.7 × Objective Score) + (0.3 × Community Score)

#### Rationale for Weighting

* The Objective Score has a higher weight (70%) to ensure providers are primarily judged by measurable performance.
* The Community Score (30%) adds a subjective element, reflecting consumers trust and satisfaction.

***

## Reporting and Transparency

#### Provider Dashboard

* Providers can view their reputation scores in a dashboard that includes:
  * Objective Reputation Score with detailed SLA compliance data.
  * Community Reputation Score with aggregated feedback and trends.

#### Public Visibility

* Consumers can view a provider's Overall Reputation Score, along with badges for exceptional performance (e.g., "100% SLA Compliance for 6 Months").

#### Dispute Resolution

* Providers can dispute inaccurate feedback or SLA violations through a formal process, which includes re-evaluating QoS records or reviewing consumers complaints.

***

## Incentives for High Reputation

* **Priority Listing**: High-reputation providers appear at the top of consumer search results.
* **Performance Bonuses**: Providers with consistently high scores may receive reduced fees or other benefits.
* **Trust Badges**: Visible indicators of reliability (e.g., "Top Performer").

This system ensures a balanced approach to evaluating providers, combining hard metrics with consumer trust to create a fair and transparent ecosystem.
