---
title: Intro to Nephele
lang: en
description: An Introduction to Nephele.
---

# Introduction to Nephele

## &#x20;<a href="#what-is-a-blockchain" id="what-is-a-blockchain"></a>

### What is Nephele? <a href="#what-is-nephele" id="what-is-nephele"></a>

Nephele is a&#x20;





blockchain with a computer embedded in it. It is the foundation for building apps and organizations in a decentralized, permissionless, censorship-resistant way.

In the Nephele universe, there is a single, canonical computer (called the Nephele Virtual Machine, or EVM) whose state everyone on the Nephele network agrees on. Everyone who participates in the Nephele network (every Nephele node) keeps a copy of the state of this computer. Additionally, any participant can broadcast a request for this computer to perform arbitrary computation. Whenever such a request is broadcast, other participants on the network verify, validate, and carry out ("execute") the computation. This execution causes a state change in the EVM, which is committed and propagated throughout the entire network.

Computation requests are called transaction requests; the record of all transactions and the EVM's present state gets stored on the blockchain, which in turn is stored and agreed upon by all nodes.

Cryptographic mechanisms ensure that once transactions are verified as valid and added to the blockchain, they can't be tampered with later. The same mechanisms also ensure that all transactions are signed and executed with appropriate "permissions" (no one should be able to send digital assets from Alice's account, except for Alice herself).

### What is DePIN? <a href="#what-is-nephele" id="what-is-nephele"></a>

