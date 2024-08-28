# Centralized Instances

_<mark style="color:red;">No endorsement of any Cloud provider is made here. The information provided is purely indicative. Please extend your research according to your needs and do not hesitate to ask questions in our social medias.</mark>_

_<mark style="color:red;">The information provided by Cloud providers is extremely approximative because of rebates and other conditions related to server usage.</mark>_&#x20;

## Centralized Providers

### To Run Network Protocol Clients (PoS-Only Nodes)

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

### To Support Storage Provision (PoS-ST Node)

Here is an example with a centralized dedicated server provider and their options and configurations that meet the minimal hardware requirements for a staking validator (in September 2024). The server setups can vary depending on how you split the sector certification into multiple workers. We also consider that the storage duties are performed with a full node.

{% tabs %}
{% tab title="OVH  - Basic" %}
**Server 1:** Data Reception and Retrieval Node, Blockchain Validation

* Market (Price and Request Management)
* Daemons (Full-Node Network Client and Sector Management Client)
* Sector Storage.

**Server 2:** Sector Management

* PoRep: Sealing Pipeline
* WindowedPoSt
* SnapDeal Pipelines

<table><thead><tr><th width="169">Configurations</th><th width="250">Server 1</th><th>Server 2</th></tr></thead><tbody><tr><td>Instance Name</td><td><strong>HGR-STOR-1</strong></td><td><strong>Scale-GPU-1</strong></td></tr><tr><td>CPU</td><td><strong>Intel Xeon Gold 6554S - 36c/72t - 2.2GHz/3GHz</strong></td><td><strong>AMD EPYC GENOA 9354 - 32c/64t - 3.25GHz/3.8GHz</strong></td></tr><tr><td>RAM</td><td><strong>128GB DDR5 ECC 4800MHz</strong></td><td><strong>384GB DDR5 ECC 4800MHz</strong></td></tr><tr><td>System + Software</td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td></tr><tr><td>Additional Storage</td><td><p><strong>36× 22TB HDD SAS</strong> </p><p><strong>2× 15.36TB SSD NVMe Soft RAID</strong></p></td><td><strong>2× 1.92TB SSD NVMe Soft RAID</strong></td></tr><tr><td>Public Bandwidth</td><td><strong>10G bit/s unlimited and guaranteed</strong></td><td><strong>1G bit/s unlimited and guaranteed</strong></td></tr><tr><td>Private Bandwidth</td><td><strong>25G bit/s unlimited and guaranteed</strong></td><td>2<strong>5G bit/s unlimited and guaranteed</strong></td></tr><tr><td>GPU</td><td>---</td><td><strong>2x Nvidia L4 24GB</strong></td></tr><tr><td>Price</td><td><strong>3100 USD/Month</strong></td><td><strong>1,500 USD/Month</strong></td></tr></tbody></table>
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

In this basic configuration, we can see running a unique Server 1 with Server 2; the storage provider must set a 5.6 USD/TB/Month price with OVH Cloud for instance. This does not consider the staking reward, the maintenance costs, and other expenses or alternative setups to reduce the costs. We'd like to invite you to read the [network economy](../../../../learn/network-economy/) model to understand how you can define a business model with the storage provision. Nonetheless, a storage provider can improve the setup with a dedicated server provider.&#x20;
