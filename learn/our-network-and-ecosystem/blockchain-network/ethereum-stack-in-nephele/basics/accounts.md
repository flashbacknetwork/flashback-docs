# Externally-Owned Accounts

<mark style="color:green;">Externally-owned account (EOA)</mark> can be controlled by anyone that owns the [private keys](https://www.investopedia.com/terms/p/private-key.asp), an elementary component of the blockchain technology. Its creation costs nothing, allows to do transactions only in NEPH tokens by the account owner only, and manage the pair private/public keys related to the account.&#x20;

This is the basic way to start a transaction or execute a smart contract.

_An EOA is not a wallet. An account is the keypair for a user-owned Nephele account. A wallet is an interface or application that lets you interact with your Nephele account._

## EOA Key Pairs <a href="#account-creation" id="account-creation"></a>

An EOA account consists of a cryptographic key pair: **a public key and a private key**. These keys ensure that a transaction was indeed authorized by the account holder and safeguard against forgery. Your private key is what you use to authorize transactions, effectively controlling access to the funds tied to your account. It's important to note that you don't actually possess the cryptocurrency itself; rather, you hold the private keys, while the funds remain securely recorded on Nephele’s blockchain.

This setup protects against fraud, as it allows the verification of the transaction's origin. For instance, if Alice wishes to transfer Nephele coins to Bob's account, she must generate a transaction request and submit it to the network for validation. Nephele’s use of public-key cryptography enables Alice to demonstrably confirm that she initiated the transaction request. Without this cryptographic protection, a malicious actor like Eve could falsely claim to transfer funds from Alice's account by broadcasting a deceptive transaction request such as “send 10 NEPH from Alice’s account to Eve’s account,” and no one would be able to confirm its legitimacy.

This cryptographic framework is crucial for maintaining the integrity and security of transactions on the blockchain.

## Account creation <a href="#account-creation" id="account-creation"></a>

When you want to create an account most libraries will generate you a random private key. A private key is made up of 64 hex characters and can be encrypted with a password.

Example:

`fffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd036415f`

The public key is generated from the private key using the [Elliptic Curve Digital Signature Algorithm](https://wikipedia.org/wiki/Elliptic\_Curve\_Digital\_Signature\_Algorithm). You get a public address for your account by taking the last 20 bytes of the Keccak-256 hash of the public key and adding `0x` to the beginning.

It is possible to derive new public keys from your private key but you cannot derive a private key from public keys. This means it's vital to keep a private key safe and, as the name suggests, **PRIVATE**.

You need a private key to sign messages and transactions which output a signature. Others can then take the signature to derive your public key, proving the author of the message. In your application, you can use a javascript library to send transactions to the network.

## The Fields in an EOA <a href="#an-account-examined" id="an-account-examined"></a>

The accounts in Nephele have two fields:

* `nonce` – A counter that indicates the number of transactions sent from an externally-owned account or the number of contracts created by a contract account. Only one transaction with a given nonce can be executed for each account, protecting against replay attacks where signed transactions are repeatedly broadcast and re-executed.
* `balance` – The number of wei owned by this address. Wei is a denomination of NEPH and there are 1e+18 wei per NEPH.
