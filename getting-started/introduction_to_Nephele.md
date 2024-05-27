---
title: Intro to Nephele
description: An Introduction to Nephele.
lang: en
---

## What is a blockchain? {#what-is-a-blockchain}

A blockchain is a public database that is updated and shared across many computers in a network.

"Block" refers to data and state being stored in consecutive groups known as "blocks". If you send NEPH to someone else, the transaction data needs to be added to a block to be successful.

"Chain" refers to the fact that each block cryptographically references its parent. In other words, blocks get chained together. The data in a block cannot change without changing all subsequent blocks, which would require the consensus of the entire network.

Every computer in the network must agree upon each new block and the chain as a whole. These computers are known as "nodes". Nodes ensure everyone interacting with the blockchain has the same data. To accomplish this distributed agreement, blockchains need a consensus mechanism.

Nephele uses a [proof-of-stake-based consensus mechanism](/developers/docs/consensus-mechanisms/pos/). Anyone who wants to add new blocks to the chain must stake NEPH - the native currency in Nephele - as collateral and run validator software. These "validators" can then be randomly selected to propose blocks that other validators check and add to the blockchain. There is a system of rewards and penalties that strongly incentivize participants to be honest and available online as much as possible.

If you would like to see how blockchain data is hashed and subsequently appended to the history of block references, be sure to check out [this demo](https://andersbrownworth.com/blockchain/blockchain) by Anders Brownworth and watch the accompanying video below.

Watch Anders explain hashes in blockchains:

<YouTube id="_160oMzblY8" />

## What is Nephele? {#what-is-Nephele}

Nephele is a blockchain with a computer embedded in it. It is the foundation for building apps and organizations in a decentralized, permissionless, censorship-resistant way.

In the Nephele universe, there is a single, canonical computer (called the Nephele Virtual Machine, or EVM) whose state everyone on the Nephele network agrees on. Everyone who participates in the Nephele network (every Nephele node) keeps a copy of the state of this computer. Additionally, any participant can broadcast a request for this computer to perform arbitrary computation. Whenever such a request is broadcast, other participants on the network verify, validate, and carry out ("execute") the computation. This execution causes a state change in the EVM, which is committed and propagated throughout the entire network.

Requests for computation are called transaction requests; the record of all transactions and the EVM's present state gets stored on the blockchain, which in turn is stored and agreed upon by all nodes.

Cryptographic mechanisms ensure that once transactions are verified as valid and added to the blockchain, they can't be tampered with later. The same mechanisms also ensure that all transactions are signed and executed with appropriate "permissions" (no one should be able to send digital assets from Alice's account, except for Alice herself).

## What is Nephele? {#what-is-Nephele}

**Nephele (NEPH)** is the native cryptocurrency of Nephele. The purpose of NEPH is to allow for a market for computation. Such a market provides an economic incentive for participants to verify and execute transaction requests and provide computational resources to the network.

Any participant who broadcasts a transaction request must also offer some amount of NEPH to the network as a bounty. The network will award this bounty to whoever eventually does the work of verifying the transaction, executing it, committing it to the blockchain, and broadcasting it to the network.

The amount of NEPH paid corresponds to the resources required to do the computation. These bounties also prevent malicious participants from intentionally clogging the network by requesting the execution of infinite computation or other resource-intensive scripts, as these participants must pay for computation resources.

NEPH is also used to provide crypto-economic security to the network in three main ways: 1) it is used as a means to reward validators who propose blocks or call out dishonest behavior by other validators; 2) It is staked by validators, acting as collateral against dishonest behavior—if validators attempt to misbehave their NEPH can be destroyed; 3) it is used to weigh 'votes' for newly proposed blocks, feeding into the fork-choice part of the consensus mechanism.


