---
author: Brieuc Berruet <brieuc.berruet@thenephelecloud.com>
---

# Smart Contracts

A **smart contract** is a self-executing contract with the terms of the agreement directly written into lines of code. These contracts operate on blockchain technology, allowing them to run automatically and transparently without intermediaries like lawyers or banks.

Nick Szabo introduced the term ["smart contract"](https://www.fon.hum.uva.nl/rob/Courses/InformationInSpeech/CDROM/Literature/LOTwinterschool2006/szabo.best.vwh.net/smart.contracts.html) in 1994, and in 1996, he wrote an exploration of what smart contracts could do. Szabo envisioned a digital marketplace where automatic, cryptographically secure processes enable transactions and business functions without trusted intermediaries.&#x20;

<mark style="color:red;">**The smart contract is also an account**</mark>, but the difference from an [EOA ](accounts.md)is that the key pairs are controlled by the network itself through its code. A smart contract is mainly deployed from an EOA. The smart contract is hosted by and for the network, allowing it to develop without limitations based on [the composability](smart-contracts.md#the-composability) principle.

## Key Characteristics of Smart Contracts

* **Automated**: They automatically execute actions when predetermined conditions are met, such as transferring funds or issuing tickets.
* **Immutable**: Once a smart contract is deployed on the blockchain, it cannot be changed; this prevents tampering and ensures all parties adhere to the original terms.
* **Distributed**: Everyone on the network validates the output of the contract, so there's no need to trust a single central authority.

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

#### 12. **Nn-Fungible Token (NFT) and Art**

* **Art Provenance and Sales**: Manage and verify the authenticity and ownership of artworks and collectibles digitally through NFTs.

## The Composability

Smart contracts are public on Ethereum and Nephele. You don't need to write your own smart contract to become a dcentralized application (dApp) developer, you just need to know how to interact with them. For example, you can use the existing smart contracts of [Uniswap](https://uniswap.exchange/swap), a decentralized exchange, to handle all the token swap logic in your application or service – you don't need to start from scratch. If you are a developer, you can imagine this as an [application programming interface (API)](https://en.wikipedia.org/wiki/API).&#x20;

### What is It? <a href="#what-is-composability" id="what-is-composability"></a>

Composability is combining distinct components to create new systems or outputs. In software development, composability means developers can reuse existing software components to build new applications. A good way to understand composability is to think of composable elements as Lego blocks. Each Lego can be combined with another, allowing you to build complex structures by combining different Legos.

Hence, every smart contract is a Lego of sorts—you can use smart contracts from other projects as building blocks for your project. This means you don't have to spend time reinventing the wheel or building from scratch.

### How does It Work? <a href="#how-does-composability-work" id="how-does-composability-work"></a>

Smart contract composability generally works off three principles: modularity, autonomy, and discoverability:

**1. Modularity**: This is the ability of individual components to perform a specific task. Every smart contract has a specific use case (as shown in the Uniswap example).

**2. Autonomy**: Composable components must be able to operate independently. Each smart contract in Nephele is self-executing and can function without relying on other parts of the system.

**3. Discoverability**: Developers cannot call external contracts or integrate software libraries into applications if the former are not publicly available. By design, smart contracts are open-source; anyone can call a smart contract or fork a codebase.

### Benefits of Composability <a href="#benefits-of-composability" id="benefits-of-composability"></a>

#### Shorter development cycle <a href="#shorter-development-cycle" id="shorter-development-cycle"></a>

Composability reduces the work that developers have to do when creating [dapps](https://ethereum.org/en/dapps/#what-are-dapps). [As Naval Ravikant puts it](https://twitter.com/naval/status/1444366754650656770) "Open source means every problem has to be solved once."

If there is a smart contract that solves one problem, other developers can reuse it, so they don’t have to solve the same problem. This way, developers can take existing software libraries and add extra functionality to create new dapps.

#### Greater innovation <a href="#greater-innovation" id="greater-innovation"></a>

Composability encourages innovation and experimentation because developers can reuse, modify, duplicate, or integrate open-source code to create desired results. As a result, development teams spend less time on basic functionality and can allocate more time experimenting with new features.

#### Better user experience <a href="#better-user-experience" id="better-user-experience"></a>

Interoperability between components of the Nephele ecosystem improves the user experience. Users can access greater functionality when apps integrate external smart contracts than in a fragmented ecosystem where applications cannot communicate.

We'll use an example from arbitrage trading to illustrate the benefits of interoperability:

If a token is trading higher on `exchange A` than `exchange B`, you can take advantage of the price difference to make profit. However, you can only do that if you have enough capital to fund the transaction (i.e., buying the token from `exchange B` and selling it on `exchange A`).

In a scenario where you don't have enough funds to cover the trade, a flash loan might be ideal. [Flash loans](https://ethereum.org/en/defi/#flash-loans) are highly technical, but the basic idea is that you can borrow assets (without collateral) and return same within _one_ transaction.

Going back to our initial example, an arbitrage trader can take out a large flash loan, buy tokens from `exchange B`, sell them on `exchange A`, pay back the capital + interest, and keep the profit, within the same transaction. This complex logic requires combining calls to multiple contracts, which wouldn't be possible if smart contracts lacked interoperability.

### Examples of Composability from the Ethereum Ecosystem <a href="#composability-in-ethereum" id="composability-in-ethereum"></a>

#### Token swaps <a href="#token-swaps" id="token-swaps"></a>

If you create a dapp that requires transactions to be paid in ETH, you can allow users to pay in other ERC-20 tokens by integrating token swap logic. The code will automatically convert the user’s token to ETH before the contract executes the called function.

#### Governance <a href="#governance" id="governance"></a>

Building bespoke governance systems for a [DAO](https://ethereum.org/en/dao/) can be expensive and time-consuming. Instead, you could use an open-source governance toolkit, such as [Aragon Client](https://client.aragon.org/), to bootstrap your DAO to quickly create a governance framework.

#### Identity management <a href="#identity-management" id="identity-management"></a>

Instead of building a custom authentication system or relying on centralized providers, you can integrate decentralized identity (DID) tools to manage authentication for users. An example is [SpruceID](https://www.spruceid.com/), an open-source toolkit which offers a "Sign in with Ethereum" functionality that lets users authenticate identities with an Ethereum wallet.

### Tutorials <a href="#related-tutorials" id="related-tutorials"></a>

* [Kickstart your dapp frontend development with create-eth-app](https://ethereum.org/en/developers/tutorials/kickstart-your-dapp-frontend-development-with-create-eth-app/) _– An overview of how to use create-eth-app to create apps with popular smart contracts out the box._

### Further Reading <a href="#further-reading" id="further-reading"></a>

_Know of a community resource that helped you? Edit this page and add it!_

* [Composability is Innovation](https://future.a16z.com/how-composability-unlocks-crypto-and-everything-else/)
* [Why Composability Matters For Web3](https://hackernoon.com/why-composability-matters-for-web3)
* [What is Composability?](https://blog.aragon.org/what-is-composability/)
