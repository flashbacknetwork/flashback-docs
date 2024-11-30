# Smart Contracts

A **smart contract** is a self-executing contract with the terms of the agreement directly written into lines of code. These contracts operate on blockchain technology, allowing them to run automatically and transparently without intermediaries like lawyers or banks.

Nick Szabo introduced the term ["smart contract"](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart.contracts.html) in 1994, and in 1996, he wrote an exploration of what smart contracts could do. Szabo envisioned a digital marketplace where automatic, cryptographically secure processes enable transactions and business functions without trusted intermediaries.

<mark style="color:red;">**The smart contract is also an account**</mark>, but the difference from an [EOA ](accounts.md)is that the key pairs are controlled by the network itself through its code. A smart contract is mainly deployed from an EOA. The smart contract is hosted by and for the network, allowing it to develop without limitations based on [the composability](smart-contracts.md#the-composability) principle.

## <mark style="color:yellow;">Key Characteristics</mark> of Smart Contracts

* <mark style="color:yellow;">**Automated**</mark><mark style="color:yellow;">:</mark> They automatically execute actions when predetermined conditions are met, such as transferring funds or issuing tickets.
* <mark style="color:yellow;">**Immutable**</mark><mark style="color:yellow;">:</mark> Once a smart contract is deployed on the blockchain, it cannot be changed; this prevents tampering and ensures all parties adhere to the original terms.
* <mark style="color:yellow;">**Distributed**</mark><mark style="color:yellow;">:</mark> Everyone on the network validates the output of the contract, so there's no need to trust a single central authority.

## Trust in Conventional Contracts

One of the biggest problems with a traditional contract is the need for trusted individuals to follow through with the contract's outcomes.

### Example:

Alice and Bob are having a bicycle race. Let's say Alice bets Bob $10 that she will win the race. Bob is confident he'll be the winner and agrees to the bet. Ultimately, Alice finishes the race well ahead of Bob and is the clear winner. But Bob refuses to pay out on the bet, claiming Alice must have cheated.

This silly example illustrates the problem with any non-smart agreement. Even if the conditions of the agreement get met (i.e., you are the winner of the race), you must still trust another person to fulfill the agreement (i.e., payout on the bet).

## The Simple Example: A Digital Vending Machine

A simple metaphor for a smart contract is a vending machine, which works somewhat similarly to a smart contract-specific inputs guarantee predetermined outputs.

1. You select a product
2. The vending machine displays the price
3. You pay the price
4. The vending machine verifies that you paid the right amount
5. The vending machine gives you your item

The vending machine will only dispense your desired product after all requirements are met. If you don't select a product or insert enough money, the vending machine won't give out your product.

***

## Others Examples

#### 1. **Financial Services**

* **Payments and Transfers**: Smart contracts can automate payments when certain conditions are met, reducing the need for intermediaries like banks.
* **Insurance Claims**: Automate the processing and payout of claims based on predefined criteria. For example, a smart contract could automatically release funds to policyholders when flight data confirms a substantial delay.
* **Loan Disbursement**: Automate credit agreements where the disbursement and repayments are managed according to the terms coded in the smart contract.

#### 2. **Supply Chain Management**

* **Tracking and Verification**: Smart contracts can track the provenance of goods as they move through the supply chain, automatically updating the status and ownership, ensuring transparency and traceability.
* **Inventory Management**: Automate ordering and payments based on inventory levels or other supply chain triggers, enhancing efficiency.

#### 3. **Real Estate**

* **Property Sales**: Facilitate the exchange of property titles and automate transactions, reducing paperwork and the potential for fraud.
* **Rental Agreements**: Automate lease agreements, where rent payments trigger automatically, and terms are enforced without a middleman.

#### 4. **Healthcare**

* **Medical Records**: Securely manage and share patient data between authorized parties, improving privacy and reducing administrative overhead.
* **Drug Supply Chain**: Ensure compliance and security in the drug supply chain by documenting every transaction in an immutable ledger.

#### 5. **Legal Industry**

* **Contract Management**: Automatically execute contractual obligations and terms, reducing the need for legal consultations for routine agreements.
* **Notarization**: Digitally notarize documents and automatically store this information in a secure, unalterable format.

#### 6. **Government Services**

* **Voting Systems**: Create tamper-proof digital voting systems where votes are securely cast, counted, and managed via smart contracts.
* **Public Records**: Automate the updating and maintenance of public records, from vehicle registrations to business licenses.

#### 7. **Digital Identity**

* **Identity Verification**: Manage identities and facilitate verification processes without revealing unnecessary personal information, enhancing privacy.

#### 8. **Entertainment and Media**

* **Royalty Distribution**: Automate royalty payments to artists and content creators based on predefined distribution formulas.
* **Digital Rights Management**: Control and automate the distribution and rights management of digital content such as music, movies, and books.

#### 9. **Gaming**

* **In-Game Transactions**: Automate transactions for in-game assets, where assets can be bought, sold, or traded on blockchain networks.
* **Decentralized Gaming Platforms**: Enable truly decentralized gaming platforms where the game logic and asset ownership are managed through smart contracts.

#### 10. **Internet of Things (IoT)**

* **Smart Appliances**: Integrate smart contracts with IoT devices to automate actions based on sensor data, such as paying utility bills based on consumption or ordering supplies.

#### 11. **Automotive Industry**

* **Car Leasing and Sales**: Automate the entire process from vehicle leasing agreements to service history tracking and payments.

#### 12. **Non-Fungible Token (NFT) and Art**

* **Art Provenance and Sales**: Manage and verify the authenticity and ownership of artworks and collectibles digitally through NFTs.

### Further Reading <a href="#further-reading" id="further-reading"></a>

* [Coinbase: What is a smart contract?](https://www.coinbase.com/learn/crypto-basics/what-is-a-smart-contract)
* [Chainlink: What is a smart contract?](https://chain.link/education/smart-contracts)
* [Video: Simply Explained - Smart Contracts](https://youtu.be/ZE2HxTmxfrI)
* [Cyfrin Updraft: Web3 learning and auditing platform](https://updraft.cyfrin.io/)
