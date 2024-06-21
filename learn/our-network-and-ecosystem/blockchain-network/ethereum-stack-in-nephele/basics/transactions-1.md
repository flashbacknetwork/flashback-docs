---
author: Brieuc Berruet <brieuc.berruet@thenephelecloud.com>
---

# Transactions

To help you better understand this page, we recommend you first read [externally-owned accounts (EOA)](accounts.md) and our [introduction](../../../../introduction/) about Nephele.

***

A transaction refers to an action initiated by an EOA to transfer a value to another EOA. For example, if Bob sends Alice 1 NEPH, Bob's account must be debited, and Alice's must be credited. This state-changing action takes place within a transaction.

Transactions need to be broadcast to the whole network. Any EOA can broadcast a request for a transaction to be executed on the decentralized ledger; after this happens, the network will validate and execute the transaction and propagate the resulting state change to the rest of the network. This process is done by including the transactions in a validated block of the decentralized ledger, the blockchain.

## Types of Transactions <a href="#types-of-transactions" id="types-of-transactions"></a>

On Nephele there are a few different types of transactions:

* <mark style="color:orange;">Regular transactions</mark> from one account to another.
* <mark style="color:orange;">Contract deployment transactions</mark> without being sent to an account, where the data field is used for the contract code.
* <mark style="color:orange;">Execution of a contract</mark> that interacts with a deployed smart contract. In this case, the account which receives the transaction is the smart contract address.

## Transaction Lifecycle <a href="#transaction-lifecycle" id="transaction-lifecycle"></a>

Once the transaction has been submitted the following happens:

1. A transaction hash is cryptographically generated with the following hash: `0x97d99bc7729211111a21b12c933c949d4f31684f1d6954ff477d0477538ff017`
2. The transaction is then broadcast by a node to the network and added to a pool of all other pending network transactions.
3. A validator must pick your transaction and include it in a block in order to verify the transaction and consider it "successful".
4. As time passes, the block containing your transaction will be upgraded to "justified" then "finalized". These upgrades make it more certain that your transaction was successful and will never be altered. Once a block is "finalized," it could only ever be changed by a network-level attack that would cost many billions of dollars.

## The Standard Fields

A submitted transaction includes the following standard fields:

* `from` – the address of the sender, that will be signing the transaction. This will be an externally-owned account as smart contract cannot send transactions.
* `to` – the receiving address (if an EOA, the transaction will transfer value. If a smart contract, the transaction will execute the contract code)
* `signature` – the sender's identifier. This is generated when the sender's private key signs the transaction and confirms the sender has authorized this transaction
* `nonce` - a sequentially incrementing counter which indicates the transaction number from the account
* `value` – amount of NEPH to transfer from sender to recipient (denominated in WEI, where 1 NEPH equals 1e+18wei)
* `input data` – optional field to include arbitrary data

The transaction is operated in the EVM which means that it must be able to be executed thanks to the rules of the EVM. In these rules, a transaction may spend gas to be effective and the following fields:

* `gasLimit` – the maximum amount of gas units that can be consumed by the transaction. The [EVM](../../../../../developers/docs/evm/opcodes/) specifies the units of gas required by each computational step
* `maxPriorityFeePerGas` - the maximum price of the consumed gas to be included as a tip to the validator
* `maxFeePerGas` - the maximum fee per unit of gas willing to be paid for the transaction (inclusive of `baseFeePerGas` and `maxPriorityFeePerGas`). For a transaction to be executed, the max fee must exceed the sum of the base fee and the tip. The transaction sender is refunded the difference between the max fee and the sum of the base fee and tip.

**Gas fees** refer to the computation a validator requires to process the transaction.  [More on Gas Fees](transactions-1.md#gas).

The transaction object will look a little like this:

```js
{
  from: "0xEA674fdDe714fd979de3EdF0F56AA9716B898ec8",
  to: "0xac03bb73b6a9e108530aff4df5077c2b3d481e5a",
  gasLimit: "21000",
  maxFeePerGas: "300",
  maxPriorityFeePerGas: "10",
  nonce: "0",
  value: "10000000000"
}
```

But a transaction object needs to be signed using the sender's private key. This proves that the transaction could only have come from the sender and was not sent fraudulently. A Nephele client like Geth or Nethermind will handle this signing process.

Example [JSON-RPC](../../../../../developers/docs/apis/json-rpc/) call:

```json
{
  "id": 2,
  "jsonrpc": "2.0",
  "method": "account_signTransaction",
  "params": [
    {
      "from": "0x1923f626bb8dc025849e00f99c25fe2b2f7fb0db",
      "gas": "0x55555",
      "maxFeePerGas": "0x1234",
      "maxPriorityFeePerGas": "0x1234",
      "input": "0xabcd",
      "nonce": "0x0",
      "to": "0x07a565b7ed7d7a678680a4c162885bedbb695fe0",
      "value": "0x1234"
    }
  ]
}
```

Example response:

```json
{
  "jsonrpc": "2.0",
  "id": 2,
  "result": {
    "raw": "0xf88380018203339407a565b7ed7d7a678680a4c162885bedbb695fe080a44401a6e4000000000000000000000000000000000000000000000000000000000000001226a0223a7c9bcf5531c99be5ea7082183816eb20cfe0bbc322e97cc5c7f71ab8b20ea02aadee6b34b45bb15bc42d9c09de4a6754e7000908da72d48cc7704971491663",
    "tx": {
      "nonce": "0x0",
      "maxFeePerGas": "0x1234",
      "maxPriorityFeePerGas": "0x1234",
      "gas": "0x55555",
      "to": "0x07a565b7ed7d7a678680a4c162885bedbb695fe0",
      "value": "0x1234",
      "input": "0xabcd",
      "v": "0x26",
      "r": "0x223a7c9bcf5531c99be5ea7082183816eb20cfe0bbc322e97cc5c7f71ab8b20e",
      "s": "0x2aadee6b34b45bb15bc42d9c09de4a6754e7000908da72d48cc7704971491663",
      "hash": "0xeba2df809e7a612a0a0d444ccfa5c839624bdc00dd29e3340d46df3870f8a30e"
    }
  }
}
```

* the `raw` is the signed transaction in [Recursive Length Prefix (RLP)](../../../../../developers/docs/data-structures-and-encoding/rlp/) encoded form
* the `tx` is the signed transaction in JSON form

With the signature hash, the transaction can be cryptographically proven that it came from the sender and submitted to the network.

### The Data Field <a href="#the-data-field" id="the-data-field"></a>

The vast majority of transactions access a contract from an externally-owned account. Most contracts are written in **Solidity**, and their data field is interpreted per the application binary interface (ABI), a JSON file that defines the functions and variables included in a smart contract. The ABI allows bytecode to be mapped into human-readable formats.

The first four bytes specify which function to call, using the hash of the function's name and arguments. You can sometimes identify the function from the selector using [this database](https://www.4byte.directory/signatures/).

The rest of the calldata is the arguments, [encoded as specified in the ABI specs](https://docs.soliditylang.org/en/latest/abi-spec.html#formal-specification-of-the-encoding). For example, lets look at [this transaction](https://etherscan.io/tx/0xd0dcbe007569fcfa1902dae0ab8b4e078efe42e231786312289b1eee5590f6a1). Use **Click to see More** to see the calldata.

The function selector is `0xa9059cbb`. There are several [known functions with this signature](https://www.4byte.directory/signatures/?bytes4\_signature=0xa9059cbb). In this case [the contract source code](https://etherscan.io/address/0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48#code) has been uploaded to Etherscan, so we know the function is `transfer(address,uint256)`.

The rest of the data is:

```
10000000000000000000000004f6742badb049791cd9a37ea913f2bac38d012792000000000000000000000000000000000000000000000000000000003b0559f4
```

According to the ABI specifications, integer values (such as addresses, which are 20-byte integers) appear in the ABI as 32-byte words, padded with zeros in the front. So we know that the `to` address is [`4f6742badb049791cd9a37ea913f2bac38d01279`](https://etherscan.io/address/0x4f6742badb049791cd9a37ea913f2bac38d01279). The `value` is 0x3b0559f4 = 990206452.

##
