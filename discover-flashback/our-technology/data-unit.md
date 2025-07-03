# Data Unit

<figure><img src="../../.gitbook/assets/Flashback Ecosystem Diagrams (20).jpg" alt=""><figcaption><p>This diagram represents the simplifed data unit submission workflow.</p></figcaption></figure>

## **Data Unit: What is it?**

The data unit is not only a storage capacity or compute service offered by the provider but provides additional information such as the quality of services, the geographical location, and more. Each data unit supports multiple reservations (e.g., Reservation 1, Reservation 2, Reservation 3), which represent allocations made by consumers for specific data storage needs.&#x20;

This elementary reservation is to build a system where the user controls their expenses and their needs. At the same time, it ensures the Providers monitor more efficiently the security and the distribution of data in its infrastructure. By extension, this can enable Providers to supply unused capacity from their infrastructure.

## Steps of the Data Unit Allocation

{% stepper %}
{% step %}
### Initial Submission

**Each provider has specific "Data Units,"** representing discrete storage capacities or compute services (e.g., S3-compatible, GCS-compatible, or other certified protocols). **Providers submits their Data Units with the API of the Flashback DePin Platform** to make their services available for reservation. This offer will then be submitted in the smart contracts by waiting for the allocation by a Consumer.

The submission of a deal requires the payment of [Unit Deal Submission Fees](../tokenomics.md). The Provider may choose to pay additional fees called [Unit Priority Fees](../tokenomics.md).&#x20;
{% endstep %}

{% step %}
### Allocation by Consumer

Consumer allocation is a two-step process:

* **Selection**: This involves choosing from a list of possible Data Units in the Marketplace.
* **Payment**: Once a Data Unit has been selected, the Consumer can pay for the Data Unit and start storing using the Bridge Node information that will appear in his interface.
{% endstep %}

{% step %}
### Consumption of the Data Unit

Using the Data Unit simply means using the information returned by the Bridge Node on the interface or via API calls. During use, the Bridge Node returns performance information to the Oracles that adds to the smart contracts to determine the Reputation Score.
{% endstep %}

{% step %}
### Data Unit Closing

The end of a Data Unit occurs when the period of use comes to an end, or following voluntary termination by the Consumer or Provider. The payment is executed and [tokenomics](../tokenomics.md) is applied.
{% endstep %}
{% endstepper %}

***

## **Interactions Between Elements**

1. **Providers ↔ Orchestrator**:
   * Providers register data units and agree to SLAs managed by the Orchestrator. Based on performance, they receive scoring and incentives.
2. **Consumers ↔ Orchestrator**:
   * Consumers reserve storage and make payments via the Orchestrator, which ensures QoS and compliance with SLAs.
3. **Consumers ↔ Platform ↔ Providers**:
   * Through the platform, consumers directly interact with data units for file transfers and storage access.
4. **Tokenomics Layer**:
   * Integrated into the Orchestrator, it manages payments from consumers, rewards for providers, and penalties for non-compliance or failure. This is a long-term feature that we are improving currently in our development iterations.

