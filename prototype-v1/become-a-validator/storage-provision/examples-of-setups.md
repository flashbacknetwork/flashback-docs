# Examples of Setups

## Centralized Cloud Providers

_<mark style="color:red;">No endorsement of any Cloud provider is made here. The information provided is purely indicative. Please extend your research according to your needs and do not hesitate to ask questions on our social medias. The information provided by Cloud providers is extremely approximative because of rebates and other conditions related to server usage.</mark>_

Here is an example with a centralized dedicated server provider and their options and configurations that meet the minimal hardware requirements for a staking validator (in September 2024). The server setups can vary depending on how you split the sector certification into multiple workers. We also consider that the storage duties are performed with a full node.

{% tabs %}
{% tab title="OVH" %}
**Server 1:** Data Reception and Retrieval Node, Blockchain Validation

* Market (Price and Request Management)
* Daemons (Full-Node Network Client and Sector Management Client)
* Sector Storage.

**Server 2:** Sector Management

* PoRep: Sealing Pipeline
* WindowedPoSt
* SnapDeal Pipelines

<table><thead><tr><th width="169">Configurations</th><th width="250">Server 1</th><th>Server 2</th></tr></thead><tbody><tr><td>Instance Name</td><td><strong>HGR-STOR-1</strong></td><td><strong>Scale-GPU-1</strong></td></tr><tr><td>CPU</td><td><strong>Intel Xeon Gold 6554S - 36c/72t - 2.2GHz/3GHz</strong></td><td><strong>AMD EPYC GENOA 9354 - 32c/64t - 3.25GHz/3.8GHz</strong></td></tr><tr><td>RAM</td><td><strong>128GB DDR5 ECC 4800MHz</strong></td><td><strong>384GB DDR5 ECC 4800MHz</strong></td></tr><tr><td>System + Software</td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td><td><strong>2x SSD NVMe 960GB Datacenter Class Soft RAID</strong></td></tr><tr><td>Additional Storage</td><td><p><strong>36× 22TB HDD SAS</strong></p><p><strong>2× 15.36TB SSD NVMe Soft RAID (50% capacity for sealing)</strong></p></td><td><strong>2× 1.92TB SSD NVMe Soft RAID</strong></td></tr><tr><td>Public Bandwidth</td><td><strong>10G bit/s unlimited and guaranteed</strong></td><td><strong>1G bit/s unlimited and guaranteed</strong></td></tr><tr><td>Private Bandwidth</td><td><strong>25G bit/s unlimited and guaranteed</strong></td><td>2<strong>5G bit/s unlimited and guaranteed</strong></td></tr><tr><td>GPU</td><td>---</td><td><strong>2x Nvidia L4 24GB</strong></td></tr><tr><td>Price</td><td>2900-<strong>3300 USD/Month</strong></td><td><strong>1,400-1,700 USD/Month</strong></td></tr></tbody></table>
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

In this basic configuration, we can see running a unique Server 1 with Server 2; the storage provider must set a 10.4-12.2 USD/TB/Month price to support the setup costs. In AWS, S3 storage is between 21 and 25 USD/TB/Month.\
\
This does not consider the staking reward, the maintenance costs, and other expenses or alternative setups to reduce the costs. We want to invite you to read the [network economy](../../network-economy/) model to understand how you can define a business model with the storage provision. Nonetheless, a storage provider can improve the setup with a dedicated server provider.

## Decentralized Cloud Providers

Soon.\


## Local Setups

A hosted setup for running a PoS-ST validator node can offer greater control and potentially lower long-term costs than a cloud service. Below, we've included for you a suggested hardware setup and estimated costs for purchasing the hardware. Additionally, I’ll provide an estimate of operating costs, such as electricity bills and maintenance, with a breakdown for four years (why not a Bitcoin cycle!).

However, the storage provision is more complex than the PoS-only full nodes. Here, we would like to show a simple setup. The following presents an architecture that can be greatly optimized but allows you to understand the costs and assess different options.

_The following setups not consider the staking reward, the maintenance costs, and other expenses or alternative setups to reduce the costs (staking other protocols, etc.). We'd like to invite you to read the_ [_network economy_](../../network-economy/) _model to understand how you can define a business model with the storage provision. Nonetheless, a storage provider can improve the setup with a dedicated server provider._

{% tabs %}
{% tab title="Minimal" %}
This first setup is based on the minimal requirements and we consider a unique server. \
\
In the mainstream components based on i7 or i9, motherboards can't support more than 128 GB of RAM which is below the specifications required for doing storage provision. Nonetheless, we can observe the [last genrations of motherboards and future generation of motherboards](https://www.tomshardware.com/pc-components/motherboards/intel-600700-series-motherboards-from-asus-now-support-256gb-of-memory) would support 256 GB RAM.&#x20;

Hence, here, the configuration is a unique server handling all the operations. Here, we do not consider specific storage or quality of storage services.

**Server 1:** Data Reception and Retrieval Node, Blockchain Validation, and Sector Management

* Market (Price and Request Management)
* Daemons (Full-Node Network Client and Sector Management Client)
* Sector Storage.
* PoRep: Sealing Pipeline
* WindowedPoSt
* SnapDeals

<table><thead><tr><th width="271">Category</th><th width="407">Server 1</th></tr></thead><tbody><tr><td>CPU</td><td><strong>Processeur Intel® Xeon® w5-2545, 30MB, 3.5/4.7 GHz</strong></td></tr><tr><td>Motherboard</td><td><strong>Pro WS W790-ACE</strong></td></tr><tr><td>RAM</td><td><strong>256GB DDR5 ECC 4800MHz</strong></td></tr><tr><td>Storage (System + Software)</td><td><strong>2x 960GB Samsung PM9A3 NVMe</strong></td></tr><tr><td>Content Delivery Storage</td><td><strong>16x</strong> <strong>Seagate</strong> <strong>Exos X24 (24TB)</strong></td></tr><tr><td>Sealed Storage (as a Backup)</td><td><strong>16x</strong> <strong>Seagate</strong> <strong>Exos X24 (24TB)</strong></td></tr><tr><td>RAID Controller</td><td><strong>Broadcom MegaRAID SAS 9460-16i</strong></td></tr><tr><td>GPU</td><td><strong>NVIDIA GEFORCE RTX4070 12 GB</strong></td></tr><tr><td>Power Supply Unit (PSU)</td><td><strong>Corsair AX1600i 1600W 80+ Titanium</strong></td></tr><tr><td>Case/Chassis</td><td><strong>Supermicro SuperChassis 846BE1C-R1K03JBOD - 24 Bay 4U + External JBOD</strong></td></tr><tr><td>Cooling</td><td><strong>Corsair Hydro Series H150i Elite Capellix (360mm Radiator)</strong></td></tr><tr><td>Fans</td><td><strong>Noctua NF-A14 Industrial PPC-3000 PWM Fans (6x)</strong></td></tr><tr><td>Network Interface</td><td><strong>Intel X710-DA2 10G Dual Port SFP+ Ethernet Adapter</strong></td></tr><tr><td>Uninterruptible Power Supply</td><td><strong>---</strong></td></tr><tr><td>Hardware Costs</td><td>$<strong>25,000 - $30,000</strong></td></tr><tr><td>Electricity</td><td><strong>100-150 USD/Month</strong></td></tr><tr><td>At Home<br>(over 4 years)</td><td><strong>620-775 USD/month</strong></td></tr><tr><td>In Colocation<br>(over 4 Years - no USP)</td><td><strong>800-1,250 USD/month</strong></td></tr></tbody></table>

In this basic configuration, the storage provider can set a 1.70-2.02 USD/TB/Month price at home, and a 2.08-4.40 USD/TB/month price in colocation**.** In AWS, S3 storage is between 21 and 25 USD/TB/Month.

However, this configuration has a large disadvantage: All the sealing processing is performed on the machine which can slowdown the system and the data retrieval performances.
{% endtab %}

{% tab title="Dual" %}
This setup reconsiders the same hardware as we have with OVH. This configuration presents higher prices but a better management of the computer power requires for storage provision. Here, the server 1 is focusing on the storage of files and lock validation while the server 2 manages the WindowedPoSt, sealing and snapdeal pipelines. \
\
**Server 1:** Data Reception and Retrieval Node, Blockchain Validation

* Market (Price and Request Management)
* Daemons (Full-Node Network Client and Sector Management Client)
* Sector Storage.

**Server 2:** Sector Management

* PoRep: Sealing Pipeline
* WindowedPoSt
* SnapDeal Pipelines

<table><thead><tr><th width="218">Category</th><th width="263">Server 1</th><th width="259">Server 2</th></tr></thead><tbody><tr><td>CPU</td><td><strong>Intel Xeon Gold 6348 - 28 cores / 56 threads - 2.6GHz / 3.5GHz</strong></td><td><strong>AMD EPYC 9354 - 32 cores / 64 threads - 3.25GHz / 3.8GHz</strong></td></tr><tr><td>Motherboard</td><td><strong>Supermicro X12SPA-T Motherboard</strong></td><td><strong>ASUS Pro WS WRX80E-SAGE SE WIFI II</strong></td></tr><tr><td>RAM</td><td><strong>128GB DDR5 ECC 4800MHz</strong></td><td><strong>384GB DDR5 ECC 4800MHz</strong></td></tr><tr><td>Storage (System + Software)</td><td><strong>2x 960GB Samsung PM9A3 NVMe</strong></td><td><strong>2x 960GB Samsung PM9A3 NVMe SSD</strong></td></tr><tr><td>Content Delivery Storage</td><td><strong>18x Seagate Exos 22TB HDD, SAS 12Gbps + 15.36TB Samsung PM1735 NVMe SSD</strong></td><td>---</td></tr><tr><td>Sealed Storage (as a Backup)</td><td><strong>18x Seagate Exos 22TB HDD, SAS 12Gbps + 15.36TB Samsung PM1735 NVMe SSD</strong></td><td><strong>---</strong></td></tr><tr><td>RAID Controller</td><td><strong>Broadcom MegaRAID SAS 9460-16i</strong></td><td>---</td></tr><tr><td>GPU</td><td>---</td><td><strong>2x Nvidia L4 24GB</strong></td></tr><tr><td>Power Supply Unit (PSU)</td><td><strong>Corsair AX1600i 1600W 80+ Titanium</strong></td><td><strong>Corsair AX1600i 1600W 80+ Titanium</strong></td></tr><tr><td>Case/Chassis</td><td><strong>Supermicro SuperChassis 846BE1C-R1K03JBOD - 24 Bay 4U + External JBOD</strong></td><td><strong>Fractal Design Define 7 XL (for desktop/rackmount hybrid use)</strong></td></tr><tr><td>Cooling</td><td><strong>Corsair Hydro Series H150i Elite Capellix (360mm Radiator)</strong></td><td><strong>Corsair Hydro Series H150i Elite Capellix (360mm Radiator)</strong></td></tr><tr><td>Fans</td><td><strong>Noctua NF-A14 Industrial PPC-3000 PWM Fans (6x)</strong></td><td><strong>Noctua NF-A14 Industrial PPC-3000 PWM Fans (3x)</strong></td></tr><tr><td>Network Interface</td><td><strong>Intel X710-DA2 10G Dual Port SFP+ Ethernet Adapter</strong></td><td><strong>Mellanox ConnectX-6 Dx EN Adapter (Dual-Port 25GbE)</strong></td></tr><tr><td>Uninterruptible Power Supply</td><td><strong>APC Smart-UPS SRT 3000VA 2.7kW Rack/Tower LCD 230V (x6)</strong></td><td><strong>APC Smart-UPS SRT 3000VA 2.7kW Rack/Tower LCD 230V (x6)</strong></td></tr><tr><td>Hardware Costs</td><td>$<strong>50,000 - $60,000</strong></td><td><strong>$30,000-$35,000</strong></td></tr><tr><td>Miscellaneous<br>Electricity</td><td><strong>$1,000</strong><br><strong>100-150 USD/Month</strong></td><td><strong>$1,000</strong><br><strong>100-$200 USD/Month</strong></td></tr><tr><td>At Home<br>(over 4 years)</td><td><strong>1,160-1,450 USD/month</strong></td><td><strong>750-950 USD/Month</strong></td></tr><tr><td>In Colocation<br>(over 4 Years - no USP)</td><td><strong>1,600-2,450 USD/month</strong></td><td><strong>1,200-1,750 USD/Month</strong></td></tr></tbody></table>

In this basic configuration, we can see running a unique Server 1 with Server 2; the storage provider must set a 4.7-5.8 USD/TB/Month price at home, and a 6.8-10.2 USD/TB/month price in colocation**.** In AWS, S3 storage is between 21 and 25 USD/TB/Month.&#x20;
{% endtab %}

{% tab title="Enhanced" %}
**Soon.**\

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

