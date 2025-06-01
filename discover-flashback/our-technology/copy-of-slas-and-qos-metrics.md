---
description: >-
  The Service Level Agreements (SLAs) and Quality of Service (QoS) metrics are
  used to evaluate and monitor providers.
hidden: true
---

# Copy of SLAs and QoS metrics

{% hint style="success" %}
With **a primary focus on storage**, we are designed to be the solution of choice for companies demanding higher controlbaility while higher spectrum of decentralized offers. Flashback helps reduce investigation time across different providers while offering to providers an easy marketplace to propose their resources.
{% endhint %}

These metrics ensure a consistent and reliable experience for consumers while providing transparency and accountability for providers.

## SLA Definitions

The following SLA parameters define the minimum standards providers must meet. The Flashback DePin platform will demand the consumers to specify the value of the different key metrics to the providers when creating a Data Unit in the smart contract. Hence, if the provider can meet the conditions, He will accept it and if not, He will decline the request.\
Conversely, the platform will enable providers to offer Data Units with their own metrics and SLA levels.

<table><thead><tr><th>Key Metrics</th><th width="499">Definitions</th></tr></thead><tbody><tr><td><strong>Latency</strong></td><td><p>The time it takes to complete a read or write operation.</p><p><strong>Example</strong>: Maximum average latency of <strong>50ms</strong> for read/write operations</p></td></tr><tr><td><strong>Upload Speed</strong></td><td><p>The speed at which data can be uploaded to the storage service.</p><p><strong>Example</strong>: Minimum speed of <strong>10 MB/s</strong> for uploads of files <strong>1 GB or smaller</strong>.</p></td></tr><tr><td><strong>Download Speed</strong></td><td><p>The speed at which data can be downloaded from the storage service.</p><p><strong>Example</strong>: Minimum speed of <strong>20 MB/s</strong> for downloads of files <strong>1 GB or smaller</strong>.</p></td></tr><tr><td><strong>Uptime</strong></td><td><p>The percentage of time the storage service is operational and accessible.</p><p><strong>Example</strong>: <strong>99.95% uptime</strong> over a rolling 30-day period.</p></td></tr><tr><td><strong>Error Rate</strong></td><td><p>The proportion of failed operations (e.g., upload, download, or delete) compared to the total operations.</p><p><strong>Example</strong>: Less than <strong>0.01% failed operations</strong> per month.</p></td></tr></tbody></table>

***

## QoS Records

The QoS records serve as the backbone for evaluating SLAs. These records are continuously generated through monitoring and probing mechanisms.

#### **Structure of QoS Records**

Each QoS record consists of the following fields:

* **Timestamp**: The exact time when the record was created.
* **Provider ID**: A unique identifier for the provider.
* **Operation Type**: The type of operation being measured (e.g., read, write, upload, download).
* **Latency**: Measured latency for the operation.
* **Throughput**: Upload or download speed, depending on the operation type.
* **Success Status**: A flag indicating whether the operation succeeded or failed.
* **Error Details** (if applicable): A description of the error, if the operation failed.

#### **Data Collection Process**

QoS data is collected through a combination of:

1. **Probing Operations**: Automated test operations reported to the platform from consumers and porviders (e.g., uploading and downloading test files) to measure latency, throughput, and error rates.
2. **System Metrics**: Real-time monitoring of uptime and operational logs.

#### **High-Level Workflow**

1. **Probing**: Scheduled probes perform read, write, upload, and download operations at regular intervals.&#x20;
2. **Measurement**: Each operation records its latency, throughput, and success status.
3. **Aggregation**: QoS records are aggregated over time to calculate averages, percentages, and trends.
4. **Validation**: Aggregated data is validated against SLA requirements found in the smart contract to determine compliance.
5. **Storage**: All QoS records are securely stored in a time-series database for long-term analysis.

#### **Reporting**

Summarized QoS rolling data will be sent to the Smart Contract for on-chain or Flashback frontend consultation.

Apart from that, other external mechanisms can be implemented to generate and send regular SLA compliance reports to Providers based on custom periods.&#x20;

The summarized data includes:

* Average latency, upload speed, and download speed over the reporting period.
* Uptime percentage.
* Error rate statistics.

***

## Enforcement

Failure to meet SLA requirements may result in penalties or reduced reputation scores (as detailed in the Reputation System documentation). Providers are encouraged to consistently monitor their performance and address any deficiencies proactively.
