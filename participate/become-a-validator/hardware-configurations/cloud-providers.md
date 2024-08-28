# Cloud Providers

_<mark style="color:red;">No endorsement of any Cloud provider is made here. The information provided is purely indicative. Please do your own research.</mark>_

_<mark style="color:red;">The information provided by Cloud providers is extremely approximative because of rebates and other conditions related to server usage.</mark>_&#x20;

## Centralized Providers

### Network Protocol Clients

Here is a non-exhaustive list of centralized Cloud providers, including Google, Amazon, and OVH Cloud, along with their options and configurations that meet the minimal hardware requirements for a staking validator (in September 2024):

{% tabs %}
{% tab title="Light" %}
<table data-view="cards" data-full-width="true"><thead><tr><th>Provider</th><th>Instance Type</th><th>CPU</th><th>RAM</th><th>Storage</th><th>Network</th><th>Operating System</th><th>Price</th></tr></thead><tbody><tr><td><a href="https://cloud.google.com/"><mark style="color:yellow;"><strong>Google Cloud (GCP)</strong></mark></a></td><td>e2-standard-2</td><td>2 vCPUs (Intel Cascade Lake or newer)</td><td>8 GB RAM</td><td>80 GB SSD</td><td>Up to 4 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$30-35/month</td></tr><tr><td><a href="https://aws.amazon.com/"><mark style="color:yellow;"><strong>Amazon Web Services (AWS)</strong></mark></a></td><td>t3.small</td><td>2 vCPUs (Intel Xeon Scalable processors)</td><td>2 GB RAM</td><td>80 GB SSD</td><td>Up to 5 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$11-15/month</td></tr><tr><td><a href="https://www.ovhcloud.com/"><mark style="color:yellow;"><strong>OVH Cloud</strong></mark></a></td><td>VLE-4</td><td>4 vCPUs (Intel Xeon Gold)</td><td>4 GB RAM</td><td>80 GB SSD</td><td> 1 Gbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$10-12/month</td></tr></tbody></table>
{% endtab %}

{% tab title="Full" %}
<table data-view="cards" data-full-width="true"><thead><tr><th>Provider</th><th>Instance Type</th><th>CPU</th><th>RAM</th><th>Storage</th><th>Network</th><th>Operating System</th><th>Price</th></tr></thead><tbody><tr><td><a href="https://cloud.google.com/"><mark style="color:yellow;"><strong>Google Cloud (GCP)</strong></mark></a></td><td>n2-standard-4</td><td>4 vCPUs (Intel Cascade Lake or newer)</td><td>16 GB RAM</td><td>500 GB SSD</td><td>2 Gbps egress with 1 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$100-200/month</td></tr><tr><td><a href="https://aws.amazon.com/"><mark style="color:yellow;"><strong>Amazon Web Services (AWS)</strong></mark></a></td><td>m5.xlarge</td><td>4 vCPUs (Intel Xeon Platinum 8000 series, Cascade Lake)</td><td>16 GB</td><td>500 GB GP2 EBS</td><td>Up to 10 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$100-200/month</td></tr><tr><td><a href="https://www.ovhcloud.com/"><mark style="color:yellow;"><strong>OVH Cloud</strong></mark></a></td><td>Rise-2</td><td>4vCPU (Intel Xeon E3-1245v5)</td><td>32 GB DDR4 ECC RAM</td><td>2 x 480 GB SSD</td><td>500 Mbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$90-110/month</td></tr></tbody></table>
{% endtab %}

{% tab title="Archive" %}
<table data-view="cards" data-full-width="true"><thead><tr><th>Provider</th><th>Instance Type</th><th>CPU</th><th>RAM</th><th>Storage</th><th>Network</th><th>Operating System</th><th>Price</th></tr></thead><tbody><tr><td><a href="https://cloud.google.com/"><mark style="color:yellow;"><strong>Google Cloud (GCP)</strong></mark></a></td><td>n2-standard-8</td><td>8 vCPUs (Intel Cascade Lake)</td><td>32 GB RAM</td><td>4 TB SSD</td><td>Up to 16 Gbps (unlimited traffic)</td><td>Ubuntu 20.04 LTS</td><td>$800-1000/month</td></tr><tr><td><a href="https://aws.amazon.com/"><mark style="color:yellow;"><strong>Amazon Web Services (AWS)</strong></mark></a></td><td>m5.2xlarge</td><td>8 vCPUs (Intel Xeon Platinum 8175M or newer)</td><td>32 GB RAM</td><td>4TB SSD (GP3)</td><td>Up to 10 Gbps (Traffic limitations on usage)</td><td>Ubuntu 20.04 LTS</td><td>$700-900/month</td></tr><tr><td><a href="https://www.ovhcloud.com/"><mark style="color:yellow;"><strong>OVH Cloud</strong></mark></a></td><td>Advance-4</td><td>6vCPU (Intel Xeon E-2276G)</td><td>32 GB DDR4 ECC 2400 MHz</td><td>4 x 1TB NVMe</td><td>1 Gbps with unlimited traffic</td><td>Ubuntu 20.04 LTS</td><td>$200-400/month</td></tr></tbody></table>
{% endtab %}
{% endtabs %}

### Storage Duties (PoS-ST Nodes)

Here is an example with a centralized dedicated server provider and their options and configurations that meet the minimal hardware requirements for a staking validator (in September 2024). The server setups can vary depending on how you split the sector certification into multiple workers. We also consider that the storage duties are performed with a full node.

{% tabs %}
{% tab title="OVH  - Basic" %}
**Server 1:** Reception and Retrieval Node

* Market (Price and Request Management)
* Daemons (Full-Node Network Client and Sector Management Client)
* Sector Storage.

**Server 2:** Sector Management

* PoRep: Sealing Pipeline
* WindowedPoSt
* SnapDeal Pipelines

<table><thead><tr><th width="169">Configurations</th><th width="250">Server 1</th><th>Server 2</th></tr></thead><tbody><tr><td>Instance Name</td><td><strong>HGR-STOR-1</strong></td><td><strong>Scale-GPU-1</strong></td></tr><tr><td>CPU</td><td><strong>Intel Xeon Gold 6554S - 36c/72t - 2.2GHz/3GHz</strong></td><td><strong>AMD EPYC GENOA 9354 - 32c/64t - 3.25GHz/3.8GHz</strong></td></tr><tr><td>RAM</td><td><strong>128GB DDR5 ECC 4800MHz</strong></td><td><strong>384GB DDR5 ECC 4800MHz</strong></td></tr><tr><td>System + Client</td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td></tr><tr><td>Additional Storage</td><td><p><strong>36× 22TB HDD SAS</strong> </p><p><strong>2× 15.36TB SSD NVMe Soft RAID</strong></p></td><td><strong>2× 1.92TB SSD NVMe Soft RAID</strong></td></tr><tr><td>Public Bandwidth</td><td><strong>10G bit/s unlimited and guaranteed</strong></td><td><strong>1G bit/s unlimited and guaranteed</strong></td></tr><tr><td>Private Bandwidth</td><td><strong>25G bit/s unlimited and guaranteed</strong></td><td>2<strong>5G bit/s unlimited and guaranteed</strong></td></tr><tr><td>GPU</td><td>---</td><td><strong>2x Nvidia L4 24GB</strong></td></tr><tr><td>Price</td><td><strong>3100 USD/Month</strong></td><td><strong>1,500 USD/Month</strong></td></tr></tbody></table>
{% endtab %}

{% tab title="Your Proposal" %}
Propose a setup that you tested! We'll integrate it to the documentation!

**Server 1:** Role

* Purpose 1
* Purpose 2

**Server 2:** Role

* Purpose 1
* Purpose 2

<table><thead><tr><th width="169">Configurations</th><th width="240">Server 1</th><th>Server 2</th></tr></thead><tbody><tr><td>Instance Name</td><td></td><td></td></tr><tr><td>CPU</td><td></td><td></td></tr><tr><td>RAM</td><td></td><td></td></tr><tr><td>System + Client</td><td></td><td></td></tr><tr><td>Additional Storage</td><td></td><td></td></tr><tr><td>Public Bandwidth</td><td></td><td></td></tr><tr><td>Private Bandwidth</td><td></td><td></td></tr><tr><td>GPU</td><td></td><td></td></tr><tr><td>Price</td><td></td><td></td></tr></tbody></table>
{% endtab %}
{% endtabs %}

In this basic configuration, we can see running a unique Server 1 with Server 2; the storage provider must set a 5.6 USD/TB/Month price with OVH Cloud for instance. This does not consider the staking reward, the maintenance costs, and other expenses or alternative setups to reduce the costs. We invite you to read the [network economy](../../../learn/network-economy/) model to understand more about how you can define a business model with the storage provision. Nonetheless, a storage provider can improve the setup with a dedicated server provider.&#x20;

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

## Cons of Using a Cloud Service Provider

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
6. **Limited Customization and Optimization:**
   * **Standardized Hardware:** Many dedicated server providers offer a limited range of hardware configurations, which may not be fully optimized for your specific needs. This can be a significant limitation if you require specialized hardware for tasks such as high-throughput data processing, low-latency operations, or specific storage requirements.
   * **Inflexible Configurations:** The lack of diverse options in dedicated servers can prevent you from achieving the best possible performance or cost-efficiency for your blockchain node. For example, you might need a specific balance of CPU, GPU, memory, and storage that isn't available in pre-configured options, leading to either underutilized resources or insufficient performance.
   * **Limited Vendor Selection:** The choice of hardware vendors and components is often restricted to what the provider offers, which can limit your ability to select the most reliable or performance-oriented components for your needs.

