# Market Actor

The **Market Actor** in Filecoin is a core component of the Filecoin network that manages the **storage and retrieval deals** between **clients (service gateways)** and **storage providers (miners)**. It is responsible for handling the economic aspects of these deals, including payments and collateral, and ensuring that both parties fulfill their obligations according to the terms of the agreements.

<mark style="color:red;">It is an abstracted entity, a</mark> <mark style="color:red;"></mark><mark style="color:red;">**pure software component**</mark> <mark style="color:red;"></mark><mark style="color:red;">implemented in Lotus (or equivalent).</mark>

## **Key Functions of the Market Actor in Filecoin**

1. **Facilitates Storage Deals:**
   * The Market Actor allows clients to propose storage deals by specifying the **data size**, **storage duration**, **price**, **collateral requirements**, and **other terms**. Storage providers can accept these deals if they agree with the terms.
   * Once a deal is accepted, the Market Actor locks the necessary **FIL tokens** (Filecoin’s native cryptocurrency) from both the client (for payment) and the storage provider (as collateral) to secure the deal.
2. **Manages Retrieval Deals:**
   * In addition to storage deals, the Market Actor also handles **retrieval deals**. These deals specify the terms for retrieving stored data, including pricing and payment methods. Clients pay storage providers to retrieve the data they stored, and the Market Actor facilitates these payments.
3. **Ensures Deal Fulfillment:**
   * The Market Actor tracks the progress of each deal, ensuring that storage providers submit the required **Proof-of-Replication (PoRep)** and **Proof-of-Spacetime (PoSt)** to prove that they are indeed storing the data as agreed.
   * If the storage provider fails to provide the necessary proofs, the Market Actor can **penalize** the provider by slashing their collateral, thus incentivizing storage providers to fulfill their commitments.
4. **Handles Payments and Collateral:**
   * **Payment Management:** When a deal is initiated, the Market Actor locks the client's funds and handles the gradual release of payments to the storage provider based on deal progress. For retrieval deals, payments are typically made using a **payment channel** model.
   * **Collateral Management:** The Market Actor requires storage providers to stake collateral for each deal. This collateral is held by the Market Actor to incentivize proper behavior. If the provider fails to meet the terms, the collateral is partially or fully forfeited.
5. **Acts as an Arbitration Layer:**
   * In cases where there is a dispute between a client and a storage provider (such as if the data is not available or not stored correctly), the Market Actor can act as an **arbitration layer** to enforce penalties or rewards based on the evidence (proofs) submitted.
6. **Supports Automated Deal Matching:**
   * The Market Actor allows for **automated deal matching** between clients and storage providers using the **Ask and Bid** model. Storage providers publish their "ask" prices (prices they are willing to accept), while clients submit "bids" (prices they are willing to pay). The Market Actor helps match these asks and bids, streamlining the process.
7. **Maintains On-Chain Records of Deals:**
   * The Market Actor keeps an **on-chain record** of all storage and retrieval deals, including their terms, status, associated payments, and collateral. This provides transparency and accountability within the Filecoin network, ensuring that all parties have access to a verifiable record of agreements.
8. **Facilitates Renewals and Extensions:**
   * The Market Actor can also handle **deal renewals and extensions**. When a deal is nearing its expiration, the client or storage provider can initiate a renewal or extension, subject to new terms or continued agreements.

## **Technical Overview**

* **Part of Filecoin’s Built-in Actors:**\
  The Market Actor is one of the **built-in actors** in Filecoin's protocol, defined within the Filecoin Specification and implemented in the **Lotus** client software (the primary implementation of the Filecoin protocol).
* **Smart Contract-Like Functionality:**\
  While not a traditional smart contract, the Market Actor behaves like one, managing state and enforcing rules for deal management on the Filecoin blockchain.
* **Interaction with Other Actors:**\
  The Market Actor interacts with other actors, such as the **Storage Miner Actor** (responsible for managing storage and mining operations) and **Account Actors** (which represent users and their balances) to coordinate the proper flow of funds, collateral, and deal statuses.
