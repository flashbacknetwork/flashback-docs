---
title: Intro to Nephele
lang: en
description: An Introduction to Nephele.
---

# Introduction to Nephele

## What is a blockchain? <a href="#what-is-a-blockchain" id="what-is-a-blockchain"></a>

A blockchain is a public database that is updated and shared across many computers in a network.

"Block" refers to data and state stored in consecutive groups known as "blocks". If you send network tokens to someone else, the transaction data must be added to a block to succeed.

"Chain" refers to the fact that each block cryptographically references its parent. In other words, blocks get chained together. The data in a block cannot change without changing all subsequent blocks, which would require the consensus of the entire network.

Every computer in the network must agree upon each new block and the chain as a whole. These computers are known as "nodes". Nodes ensure everyone interacting with the blockchain has the same data. To accomplish this distributed agreement, blockchains need a consensus mechanism.

Nephele uses a proof-of-stake-spacetime-based consensus mechanism. Anyone who wants to add new blocks to the chain must stake NEPH - the native currency in Nephele - as collateral and run validator software. These "validators" can then be randomly selected to propose blocks that other validators check and add to the blockchain. There is a system of rewards and penalties that strongly incentivize participants to be honest and available online as much as possible.

If you would like to see how blockchain data is hashed and subsequently appended to the history of block references, be sure to check out [this demo](https://andersbrownworth.com/blockchain/blockchain) by Anders Brownworth and watch the accompanying video below.

Watch Anders explain hashes in blockchains:

### What is Nephele? <a href="#what-is-nephele" id="what-is-nephele"></a>

Nephele is a blockchain with a computer embedded in it. It is the foundation for building apps and organizations in a decentralized, permissionless, censorship-resistant way.

In the Nephele universe, there is a single, canonical computer (called the Nephele Virtual Machine, or EVM) whose state everyone on the Nephele network agrees on. Everyone who participates in the Nephele network (every Nephele node) keeps a copy of the state of this computer. Additionally, any participant can broadcast a request for this computer to perform arbitrary computation. Whenever such a request is broadcast, other participants on the network verify, validate, and carry out ("execute") the computation. This execution causes a state change in the EVM, which is committed and propagated throughout the entire network.

Computation requests are called transaction requests; the record of all transactions and the EVM's present state gets stored on the blockchain, which in turn is stored and agreed upon by all nodes.

Cryptographic mechanisms ensure that once transactions are verified as valid and added to the blockchain, they can't be tampered with later. The same mechanisms also ensure that all transactions are signed and executed with appropriate "permissions" (no one should be able to send digital assets from Alice's account, except for Alice herself).

### What is DePIN? <a href="#what-is-nephele" id="what-is-nephele"></a>

