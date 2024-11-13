# Composability



Smart contracts are public on Ethereum and Flashback. You don't need to write your smart contract to become a dcentralized application (dApp) developer, you need to know how to interact with them. For example, you can use the existing smart contracts of [Uniswap](https://uniswap.exchange/swap), a decentralized exchange, to handle all the token swap logic in your application or service – you don't need to start from scratch. If you are a developer, you can imagine this as an [application programming interface (API)](https://en.wikipedia.org/wiki/API).&#x20;

## What is It? <a href="#what-is-composability" id="what-is-composability"></a>

Composability is combining distinct components to create new systems or outputs. Composability means developers can reuse existing software components to build new applications in software development. An excellent way to understand composability is to think of composable elements as Lego blocks. Each Lego can be combined with another, allowing you to build complex structures by combining different Legos.

Hence, every smart contract is a Lego of sorts—you can use smart contracts from other projects as building blocks for your project. This means you don't have to spend time reinventing the wheel or building from scratch.

## How does It Work? <a href="#how-does-composability-work" id="how-does-composability-work"></a>

<mark style="color:yellow;">**Smart contract composability**</mark> generally works off <mark style="color:yellow;">**three principles**</mark>:&#x20;

* <mark style="color:yellow;">**Modularity**</mark><mark style="color:yellow;">:</mark> This is the ability of individual components to perform a specific task. Every smart contract has a specific use case (as shown in the Uniswap example).
* <mark style="color:yellow;">**Autonomy**</mark><mark style="color:yellow;">:</mark> Composable components must be able to operate independently. Each smart contract is self-executing and can function without relying on other parts of the system.
* <mark style="color:yellow;">**Discoverability**</mark><mark style="color:yellow;">:</mark> Developers cannot call external contracts or integrate software libraries into applications if the former are not publicly available. By design, smart contracts are open-source; anyone can call a smart contract or fork a codebase.

## Benefits of Composability <a href="#benefits-of-composability" id="benefits-of-composability"></a>

### Shorter development cycle <a href="#shorter-development-cycle" id="shorter-development-cycle"></a>

Composability reduces the work that developers have to do when creating [dapps](https://ethereum.org/en/dapps/#what-are-dapps). [As Naval Ravikant puts it](https://twitter.com/naval/status/1444366754650656770) "Open source means every problem has to be solved once."

If there is a smart contract that solves one problem, other developers can reuse it, so they don’t have to solve the same problem. This way, developers can take existing software libraries and add extra functionality to create new dapps.

### Greater innovation <a href="#greater-innovation" id="greater-innovation"></a>

Composability encourages innovation and experimentation because developers can reuse, modify, duplicate, or integrate open-source code to create desired results. As a result, development teams spend less time on basic functionality and can allocate more time experimenting with new features.

### Better user experience <a href="#better-user-experience" id="better-user-experience"></a>

Interoperability between components of the Ethereum or Flashback ecosystems improve the user experience. Users can access greater functionality when apps integrate external smart contracts than in a fragmented ecosystem where applications cannot communicate.

We'll use an example from arbitrage trading to illustrate the benefits of interoperability:

If a token is trading higher on `exchange A` than `exchange B`, you can take advantage of the price difference to make a profit. However, you can only do that if you have enough capital to fund the transaction (i.e., buying the token from `exchange B` and selling it on `exchange A`).

In a scenario where you don't have enough funds to cover the trade, a flash loan might be ideal. [Flash loans](https://ethereum.org/en/defi/#flash-loans) are highly technical, but the basic idea is to borrow assets (without collateral) and return same within _one_ transaction.

Going back to our initial example, an arbitrage trader can take out a large flash loan, buy tokens from `exchange B`, sell them on `exchange A`, pay back the capital + interest, and keep the profit, within the same transaction. This complex logic requires combining calls to multiple contracts, which wouldn't be possible if smart contracts lacked interoperability.

## Examples of Composability from the Ethereum Ecosystem <a href="#composability-in-ethereum" id="composability-in-ethereum"></a>

### Token swaps <a href="#token-swaps" id="token-swaps"></a>

If you create a dapp that requires transactions to be paid in NEPH, you can allow users to pay in other ERC-20 tokens by integrating token swap logic. The code will automatically convert the user’s token to NEPH before the contract executes the called function.

### Governance <a href="#governance" id="governance"></a>

Building bespoke governance systems for a [DAO](https://ethereum.org/en/dao/) can be expensive and time-consuming. Instead, you could use an open-source governance toolkit, such as [Aragon Client](https://client.aragon.org/), to bootstrap your DAO to quickly create a governance framework.

### Identity management <a href="#identity-management" id="identity-management"></a>

Instead of building a custom authentication system or relying on centralized providers, you can integrate decentralized identity (DID) tools to manage authentication for users. An example is [SpruceID](https://www.spruceid.com/), an open-source toolkit which offers a "Sign in with Ethereum" functionality that lets users authenticate identities with an Ethereum wallet.

## Tutorials <a href="#related-tutorials" id="related-tutorials"></a>

* [Kickstart your dapp frontend development with create-eth-app](https://ethereum.org/en/developers/tutorials/kickstart-your-dapp-frontend-development-with-create-eth-app/) _– An overview of how to use create-eth-app to create apps with popular smart contracts out the box._

## Further Reading <a href="#further-reading" id="further-reading"></a>

_Know of a community resource that helped you? Edit this page and add it!_

* [Composability is Innovation](https://future.a16z.com/how-composability-unlocks-crypto-and-everything-else/)
* [Why Composability Matters For Web3](https://hackernoon.com/why-composability-matters-for-web3)
* [What is Composability?](https://blog.aragon.org/what-is-composability/)
