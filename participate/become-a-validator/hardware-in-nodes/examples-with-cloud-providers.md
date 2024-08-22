# Examples with Cloud Providers

_<mark style="color:red;">No endorsement of any Cloud provider is made here. The information provided is purely indicative. Please do your own research.</mark>_

Here is a comprehensive list of server providers, including Google, Amazon, Microsoft, DigitalOcean, Hetzner, and OVH Cloud, along with their options and configurations that meet the minimal hardware requirements for a staking validator full node (in September 2024):

{% tabs %}
{% tab title="Light" %}
<table data-view="cards" data-full-width="true"><thead><tr><th>Provider</th><th>Instance Type</th><th>CPU</th><th>RAM</th><th>Storage</th><th>Network</th><th>Operating System</th><th>Price</th></tr></thead><tbody><tr><td><a href="https://cloud.google.com/"><mark style="color:yellow;"><strong>Google Cloud (GCP)</strong></mark></a></td><td>e2-standard-2</td><td>2 vCPUs (Intel Cascade Lake or newer)</td><td>8 GB RAM</td><td>50 GB SSD</td><td>Up to 1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$30-35/month</td></tr><tr><td><a href="https://aws.amazon.com/"><mark style="color:yellow;"><strong>Amazon Web Services (AWS)</strong></mark></a></td><td>t3.small</td><td>2 vCPUs (Intel Xeon Scalable processors)</td><td>2 GB RAM</td><td>50 GB SSD</td><td>Up to 5 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$11-15/month</td></tr><tr><td><a href="https://azure.microsoft.com/"><mark style="color:yellow;"><strong>Microsoft Azure</strong></mark></a></td><td>B2s</td><td>2 vCPUs (Intel Xeon E5-2673 v4 or newer)</td><td>4 GB RAM</td><td>50 GB SSD</td><td>Up to 1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$26-30/month</td></tr><tr><td><a href="https://www.alibabacloud.com/"><mark style="color:yellow;"><strong>Alibaba Cloud</strong></mark></a></td><td>ecs.t6-c1m1.large</td><td>2 vCPUs (Intel Xeon Platinum 8269CY or similar)</td><td>16 GB</td><td>50 GB SSD</td><td>1 Mbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$13-16/month</td></tr><tr><td><a href="https://www.vultr.com/"><mark style="color:yellow;"><strong>Vultr</strong></mark></a></td><td>High Frequency Compute</td><td>2 vCPUs (Intel Xeon with a high clock speed)</td><td>16 GB RAM</td><td>50 GB SSD</td><td>1 Gbps (3 TB max/month)</td><td>Ubuntu 20.04 LTS</td><td>$11-13/month</td></tr><tr><td><a href="https://www.hetzner.com/"><mark style="color:yellow;"><strong>Hetzner</strong></mark></a></td><td>CX21</td><td>2 vCPUs (Intel Xeon or AMD EPYC)</td><td>2 GB RAM</td><td>50 GB SSD</td><td>1 Gbps (20 TB max/month)</td><td>Ubuntu 20.04 LTS</td><td>$4-6/month</td></tr><tr><td><a href="https://www.ovhcloud.com/"><mark style="color:yellow;"><strong>OVH Cloud</strong></mark></a></td><td>VPS Essential</td><td>2 vCPUs (Intel Xeon Gold)</td><td>2 GB RAM</td><td>50 GB SSD</td><td>100 Mbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$3.5-5/month</td></tr><tr><td><a href="https://www.digitalocean.com/"><mark style="color:yellow;"><strong>DigitalOcean</strong></mark></a></td><td>Basic Droplet</td><td>2 vCPUs (Intel/AMD with a clock speed of 2.6 GHz or higher)</td><td>2 GB RAM</td><td>50 GB SSD</td><td>1 Gbps (1 TB/month)</td><td>Ubuntu 20.04 LTS</td><td>$9-11/month</td></tr><tr><td><a href="https://www.scaleway.com/"><mark style="color:yellow;"><strong>Scaleway</strong></mark></a></td><td>Development Instances</td><td>2 vCPUs (Intel Xeon)</td><td>2 GB RAM</td><td>50 GB SSD</td><td>0.25 Gbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$3.5-5/month</td></tr></tbody></table>
{% endtab %}

{% tab title="Full" %}
<table data-view="cards" data-full-width="true"><thead><tr><th>Provider</th><th>Instance Type</th><th>CPU</th><th>RAM</th><th>Storage</th><th>Network</th><th>Operating System</th><th>Price</th></tr></thead><tbody><tr><td><a href="https://cloud.google.com/"><mark style="color:yellow;"><strong>Google Cloud (GCP)</strong></mark></a></td><td>n2-standard-4</td><td>4 vCPUs (Intel Cascade Lake or newer)</td><td>16 GB RAM</td><td>500 GB SSD</td><td>2 Gbps egress with 1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$130-160/month</td></tr><tr><td><a href="https://aws.amazon.com/"><mark style="color:yellow;"><strong>Amazon Web Services (AWS)</strong></mark></a></td><td>m5.xlarge</td><td>4 vCPUs (Intel Xeon Platinum 8000 series, Cascade Lake)</td><td>16 GB</td><td>500 GB GP2 EBS</td><td>Up to 10 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$150-160/month</td></tr><tr><td><a href="https://azure.microsoft.com/"><mark style="color:yellow;"><strong>Microsoft Azure</strong></mark></a></td><td>Standard_D4s_v3</td><td>4 vCPUs (Intel Xeon Platinum 8000 series, Cascade Lake or newer)</td><td>16 GB RAM</td><td>512 GB Premium SSD</td><td>Up to 1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$150-170/month</td></tr><tr><td><a href="https://www.alibabacloud.com/"><mark style="color:yellow;"><strong>Alibaba Cloud</strong></mark></a></td><td>ecs.g6.xlarge</td><td>4 vCPUs (Intel Xeon Platinum 8269CY or newer)</td><td>16 GB</td><td>500 GB Ultra Cloud Disk</td><td>1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$100-120/month</td></tr><tr><td><a href="https://www.vultr.com/"><mark style="color:yellow;"><strong>Vultr</strong></mark></a></td><td>High-Performance Cloud Compute Instance</td><td>4 vCPUs (Intel Xeon or newer)</td><td>16 GB RAM</td><td>512 GB NVMe SSD</td><td>1 Gbps (5TB max/month)</td><td>Ubuntu 20.04 LTS</td><td>$120-140/month</td></tr><tr><td><a href="https://www.hetzner.com/"><mark style="color:yellow;"><strong>Hetzner</strong></mark></a></td><td>AX41-NVMe</td><td>6vCPU (AMD Ryzen 5 3600)</td><td>32 GB DDR4 RAM</td><td>2 x 1 TB NVMe SSD</td><td>1 Gbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$50-65/month</td></tr><tr><td><a href="https://www.ovhcloud.com/"><mark style="color:yellow;"><strong>OVH Cloud</strong></mark></a></td><td>Rise-2</td><td>4vCPU (Intel Xeon E3-1245v5)</td><td>32 GB DDR4 ECC RAM</td><td>2 x 480 GB SSD</td><td>500 Mbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$90-110/month</td></tr><tr><td><a href="https://www.digitalocean.com/"><mark style="color:yellow;"><strong>DigitalOcean</strong></mark></a></td><td>CPU-Optimized Droplet</td><td>4 vCPUs (Intel Cascade Lake)</td><td>16 GB RAM</td><td>500 GB SSD</td><td>1 Gbps (5 TB/month)</td><td>Ubuntu 20.04 LTS</td><td>$110-130/month</td></tr><tr><td><a href="https://www.scaleway.com/"><mark style="color:yellow;"><strong>Scaleway</strong></mark></a></td><td>DEV1-L</td><td>4 vCPUs (Intel Xeon Gold 6140 or similar)</td><td>16 GB RAM</td><td>500 GB SSD</td><td>400 Mbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$50-60/month</td></tr></tbody></table>
{% endtab %}

{% tab title="Archive" %}

{% endtab %}
{% endtabs %}



## Pros of Using a Cloud Service Provider

1. **Ease of Setup and Management**:
   * **Quick Deployment**: Cloud providers offer pre-configured instances that can be quickly deployed, reducing the time and effort required to set up a node.
   * **Managed Infrastructure**: Providers handle hardware maintenance, updates, and potential issues, allowing you to focus on running your node without worrying about hardware failures or physical maintenance.
2. **Scalability**:
   * **Flexible Resource Allocation**: Cloud services allow you to easily scale resources up or down (e.g., CPU, RAM, storage) based on your needs, making it simple to adjust to changing workloads.
   * **Geographic Distribution**: You can deploy nodes in multiple regions worldwide, which can enhance the decentralization and reliability of the network.
3. **Reliability and Uptime**:
   * **High Availability**: Major cloud providers offer robust Service Level Agreements (SLAs) with guaranteed uptime, ensuring that your node remains operational with minimal downtime.
   * **Backup and Redundancy**: Built-in backup and failover options help protect against data loss and ensure continuous operation.
4. **Security**:
   * **Physical Security**: Data centers managed by reputable cloud providers offer high levels of physical security, reducing the risk of unauthorized access to your hardware.
   * **Network Security**: Cloud providers offer built-in firewalls, DDoS protection, and other security features to help protect your node from network-based attacks.
5. **Cost-Effectiveness for Short-Term or Small-Scale Operations**:
   * **No Upfront Hardware Costs**: There is no need to invest in expensive hardware, which can be particularly advantageous for small-scale operations or those testing the waters.
   * **Pay-as-You-Go**: Cloud providers typically charge on a pay-as-you-go basis, allowing you to only pay for the resources you use.

### Cons of Using a Cloud Service Provider

1. **Potential for Higher Long-Term Costs**:
   * **Ongoing Expenses**: While cloud providers are cost-effective for short-term or small-scale operations, the costs can add up over time, especially if you require high-performance configurations or extensive data storage.
   * **Bandwidth Costs**: Data transfer costs can be high, especially if your node frequently interacts with the network (e.g., submitting blocks, downloading the blockchain).
2. **Centralization Risk**:
   * **Dependence on a Single Provider**: Relying on a single cloud provider can introduce centralization risks, as your node's operation depends on the provider's infrastructure and policies.
   * **Regulatory Risks**: Governments or other entities could pressure cloud providers to restrict or monitor blockchain activities, potentially affecting the neutrality and security of your node.
3. **Limited Control**:
   * **Lack of Hardware Access**: You have no direct access to the physical hardware, which can be a disadvantage if you require custom hardware configurations or need to perform specific optimizations.
   * **Dependency on Provider's Network**: Your node’s performance and connectivity are tied to the provider’s network infrastructure, which may not always meet the specific needs of a blockchain node.
4. **Security Concerns**:
   * **Shared Infrastructure**: Using a public cloud means your node is running on shared infrastructure, which may pose additional security risks compared to dedicated or private hardware.
   * **Trust Issues**: You must trust the cloud provider to protect your data and maintain the security of their infrastructure. Any vulnerabilities in the provider’s systems could potentially impact your node.
5. **Regulatory Challenges**:
   * **Data Sovereignty**: Depending on where the cloud provider's data centers are located, there may be legal and regulatory implications for your node's stored and processed data.
   * **Provider Policies**: Cloud providers may have policies that conflict with your use case, particularly if your node is involved in regulated or restricted activities in certain jurisdictions.

***

## By Using a Homemade Setup

A homemade setup for running a PoS validator node can offer greater control and potentially lower long-term costs thana cloud service. I've included below a suggested hardware setup along with estimated costs for purchasing the hardware. Additionally, I’ll provide an estimate of operating costs such as electricity bills and maintenance, with a breakdown for 2 years and 5 years.

### Hardware Requirements and Costs



| Type                | Caracteristics                             | Costs  |
| ------------------- | ------------------------------------------ | ------ |
| **Processor (CPU)** | Intel Core i5-12600K (6 cores, 12 threads) | \~$260 |
| **Memory (RAM)**    | 16GB DDR4 RAM (2 x 8GB, 3200MHz)           | \~$60  |
| **Storage**         | 1TB NVMe SSD (Samsung 970 EVO Plus)        |        |
|                     |                                            |        |
|                     |                                            |        |
|                     |                                            |        |



**3. Storage**

* **1TB NVMe SSD (Samsung 970 EVO Plus)**
* **Cost**: \~$100

**4. Motherboard**

* **ASUS Prime Z690-P**
* **Cost**: \~$170

**5. Power Supply Unit (PSU)**

* **EVGA 500 W1, 80+ WHITE 500W**
* **Cost**: \~$40

**6. Cooling System**

* **Cooler Master Hyper 212 RGB CPU Cooler**
* **Cost**: \~$50

**7. Case**

* **Mid-Tower ATX Case (Corsair Carbide Series 275R)**
* **Cost**: \~$70

**8. Uninterruptible Power Supply (UPS)**

* **APC UPS 600VA**
* **Cost**: \~$80

**9. Networking**

* **Gigabit Ethernet (integrated)**
* **No additional cost (assumed to be part of the motherboard)**

**10. Operating System**

* **Ubuntu Linux (Free)**
* **Cost**: $0
