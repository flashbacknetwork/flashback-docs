---
author: Brieuc Berruet <brieuc.berruet@thenephelecloud.com>
---

# Transactions, Gas, and Fees

To help you better understand this page, we recommend you first read [externally-owned accounts (EOA)](accounts.md) and our [introduction](../../../../introduction/) about Nephele.

***

## Transactions

A transaction refers to an action initiated by an EOA to transfer a value to another EOA. For example, if Bob sends Alice 1 NEPH, Bob's account must be debited, and Alice's must be credited. This state-changing action takes place within a transaction.&#x20;

Transactions need to be broadcast to the whole network. Any EOA can broadcast a request for a transaction to be executed on the decentralized ledger; after this happens, the network will validate and execute the transaction and propagate the resulting state change to the rest of the network. This process is done by including the transactions in a validated block of the decentralized ledger, the blockchain.

### Types of Transactions <a href="#types-of-transactions" id="types-of-transactions"></a>

On Nephele there are a few different types of transactions:

* <mark style="color:orange;">Regular transactions</mark> from one account to another.
* <mark style="color:orange;">Contract deployment transactions</mark> without being sent to an account, where the data field is used for the contract code.
* <mark style="color:orange;">Execution of a contract</mark> that interacts with a deployed smart contract. In this case, the account which receives the transaction is the smart contract address.

### Transaction Lifecycle <a href="#transaction-lifecycle" id="transaction-lifecycle"></a>

Once the transaction has been submitted the following happens:

1. A transaction hash is cryptographically generated with the following hash: `0x97d99bc7729211111a21b12c933c949d4f31684f1d6954ff477d0477538ff017`
2. The transaction is then broadcast by a node to the network and added to a pool of all other pending network transactions.
3. A validator must pick your transaction and include it in a block in order to verify the transaction and consider it "successful".
4. As time passes, the block containing your transaction will be upgraded to "justified" then "finalized". These upgrades make it more certain that your transaction was successful and will never be altered. Once a block is "finalized," it could only ever be changed by a network-level attack that would cost many billions of dollars.

### The Standard Fields

A submitted transaction includes the following standard fields:

* `from` – the address of the sender, that will be signing the transaction. This will be an externally-owned account as smart contract cannot send transactions.
* `to` – the receiving address (if an EOA, the transaction will transfer value. If a smart contract, the transaction will execute the contract code)
* `signature` – the identifier of the sender. This is generated when the sender's private key signs the transaction and confirms the sender has authorized this transaction
* `nonce` - a sequentially incrementing counter which indicates the transaction number from the account
* `value` – amount of NEPH to transfer from sender to recipient (denominated in WEI, where 1ETH equals 1e+18wei)
* `input data` – optional field to include arbitrary data

The transaction is operated in the EVM which means that it must be able to be executed thanks to the rules of the EVM. In these rules, a transaction may spend gas to be effective and the following fields:

* `gasLimit` – the maximum amount of gas units that can be consumed by the transaction. The [EVM](../../../../../developers/docs/evm/opcodes/) specifies the units of gas required by each computational step
* `maxPriorityFeePerGas` - the maximum price of the consumed gas to be included as a tip to the validator
* `maxFeePerGas` - the maximum fee per unit of gas willing to be paid for the transaction (inclusive of `baseFeePerGas` and `maxPriorityFeePerGas`)

Gas is a reference to the computation required to process the transaction by a validator. Users have to pay a fee for this computation. The `gasLimit`, and `maxPriorityFeePerGas` determine the maximum transaction fee paid to the validator. [More on Gas](../../../../../developers/docs/gas/).

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

***

## Gas

Gas is essential to the Nephele network. It is the fuel that allows it to operate, in the same way that a car needs gasoline to run.

## Prerequisites {#prerequisites}

To better understand this page, we recommend you first read up on [transactions](/developers/docs/transactions/) and the [EVM](/developers/docs/evm/).

## What is gas? {#what-is-gas}

Gas refers to the unit that measures the amount of computational effort required to execute specific operations on the Nephele network.

Since each Nephele transaction requires computational resources to execute, those resources have to be paid for to ensure Nephele is not vulnerable to spam and cannot get stuck in infinite computational loops. Payment for computation is made in the form of a gas fee.

The gas fee is **the amount of gas used to do some operation, multiplied by the cost per unit gas**. The fee is paid regardless of whether a transaction succeeds or fails.

![A diagram showing where gas is needed in EVM operations](./gas.png)

Gas fees have to be paid in Nephele's native currency, Nephele (NEPH). Gas prices are usually quoted in gwei, which is a denomination of NEPH. Each gwei is equal to one-billionth of an NEPH (0.000000001 NEPH or 10<sup>-9</sup> NEPH).

For example, instead of saying that your gas costs 0.000000001 Nephele, you can say your gas costs 1 gwei.

The word 'gwei' is a contraction of 'giga-wei', meaning 'billion wei'. One gwei is equal to one billion wei. Wei itself (named after [Wei Dai](https://wikipedia.org/wiki/Wei_Dai), creator of [b-money](https://www.investopedia.com/terms/b/bmoney.asp)) is the smallest unit of NEPH.

## How are gas fees calculated? {#how-are-gas-fees-calculated}

You can set the amount of gas you are willing to pay when you submit a transaction. By offering a certain amount of gas, you are bidding for your transaction to be included in the next block. If you offer too little, validators are less likely to choose your transaction for inclusion, meaning your transaction may execute late or not at all. If you offer too much, you might waste some NEPH. So, how can you tell how much to pay?

The total gas you pay is divided into two components: the `base fee` and the `priority fee` (tip).

The `base fee` is set by the protocol - you have to pay at least this amount for your transaction to be considered valid. The `priority fee` is a tip that you add to the base fee to make your transaction attractive to validators so that they choose it for inclusion in the next block.

A transaction that only pays the `base fee` is technically valid but unlikely to be included because it offers no incentive to the validators to choose it over any other transaction. The 'correct' `priority` fee is determined by the network usage at the time you send your transaction - if there is a lot of demand then you might have to set your `priority` fee higher, but when there is less demand you can pay less.

For example, let's say Jordan has to pay Taylor 1 NEPH. An NEPH transfer requires 21,000 units of gas, and the base fee is 10 gwei. Jordan includes a tip of 2 gwei.

The total fee would now be equal to:

`units of gas used * (base fee + priority fee)`

where the `base fee` is a value set by the protocol and the `priority fee` is a value set by the user as a tip to the validator.

i.e. `21,000 * (10 + 2) = 252,000 gwei` (0.000252 NEPH).

When Jordan sends the money, 1.000252 NEPH will be deducted from Jordan's account. Taylor will be credited 1.0000 NEPH. The validator receives the tip of 0.000042 NEPH. The `base fee` of 0.00021 NEPH is burned.

### Base fee {#base-fee}

Every block has a base fee which acts as a reserve price. To be eligible for inclusion in a block the offered price per gas must at least equal the base fee. The base fee is calculated independently of the current block and is instead determined by the blocks before it - making transaction fees more predictable for users. When the block is created this **base fee is "burned"**, removing it from circulation.

The base fee is calculated by a formula that compares the size of the previous block (the amount of gas used for all the transactions) with the target size. The base fee will increase by a maximum of 12.5% per block if the target block size is exceeded. This exponential growth makes it economically non-viable for block size to remain high indefinitely.

| Block Number | Included Gas | Fee Increase | Current Base Fee |
| ------------ | -----------: | -----------: | ---------------: |
| 1            |          15M |           0% |         100 gwei |
| 2            |          30M |           0% |         100 gwei |
| 3            |          30M |        12.5% |       112.5 gwei |
| 4            |          30M |        12.5% |       126.6 gwei |
| 5            |          30M |        12.5% |       142.4 gwei |
| 6            |          30M |        12.5% |       160.2 gwei |
| 7            |          30M |        12.5% |       180.2 gwei |
| 8            |          30M |        12.5% |       202.7 gwei |

Following the table above - to create a transaction on block number 9, a wallet will let the user know with certainty that the **maximum base fee** to be added to the next block is `current base fee * 112.5%` or `202.7 gwei * 112.5% = 228.1 gwei`.

It's also important to note it is unlikely we will see extended spikes of full blocks because of the speed at which the base fee increases preceding a full block.

| Block Number | Included Gas | Fee Increase | Current Base Fee |
| ------------ | -----------: | -----------: | ---------------: |
| 30           |          30M |        12.5% |      2705.6 gwei |
| ...          |          ... |        12.5% |              ... |
| 50           |          30M |        12.5% |     28531.3 gwei |
| ...          |          ... |        12.5% |              ... |
| 100          |          30M |        12.5% |  10302608.6 gwei |

### Priority fee (tips) {#priority-fee}

The priority fee (tip) incentivizes validators to include a transaction in the block. Without tips, validators would find it economically viable to mine empty blocks, as they would receive the same block reward. Small tips give validators a minimal incentive to include a transaction. For transactions to be preferentially executed ahead of other transactions in the same block, a higher tip can be added to try to outbid competing transactions.

### Max fee {#maxfee}

To execute a transaction on the network, users can specify a maximum limit they are willing to pay for their transaction to be executed. This optional parameter is known as the `maxFeePerGas`. For a transaction to be executed, the max fee must exceed the sum of the base fee and the tip. The transaction sender is refunded the difference between the max fee and the sum of the base fee and tip.

### Block size {#block-size}

Each block has a target size of 15 million gas, but the size of blocks will increase or decrease in accordance with network demand, up until the block limit of 30 million gas (2x the target block size). The protocol achieves an equilibrium block size of 15 million on average through the process of _tâtonnement_. This means if the block size is greater than the target block size, the protocol will increase the base fee for the following block. Similarly, the protocol will decrease the base fee if the block size is less than the target block size. The amount by which the base fee is adjusted is proportional to how far the current block size is from the target. [More on blocks](/developers/docs/blocks/).

### Calculating gas fees in practice {#calculating-fees-in-practice}

You can explicitly state how much you are willing to pay to get your transaction executed. However, most wallet providers will automatically set a recommended transaction fee (base fee + recommended priority fee) to reduce the amount of complexity burdened onto their users.

## Why do gas fees exist? {#why-do-gas-fees-exist}

In short, gas fees help keep the Nephele network secure. By requiring a fee for every computation executed on the network, we prevent bad actors from spamming the network. In order to avoid accidental or hostile infinite loops or other computational wastage in code, each transaction is required to set a limit to how many computational steps of code execution it can use. The fundamental unit of computation is "gas".

Although a transaction includes a limit, any gas not used in a transaction is returned to the user (i.e. `max fee - (base fee + tip)` is returned).

![Diagram showing how unused gas is refunded](../transactions/gas-tx.png)
_Diagram adapted from [Nephele EVM illustrated](https://takenobu-hs.github.io/downloads/ethereum_evm_illustrated.pdf)_

## What is the gas limit? {#what-is-gas-limit}

The gas limit refers to the maximum amount of gas you are willing to consume on a transaction. More complicated transactions involving [smart contracts](/developers/docs/smart-contracts/) require more computational work, so they require a higher gas limit than a simple payment. A standard NEPH transfer requires a gas limit of 21,000 units of gas.

For example, if you put a gas limit of 50,000 for a simple NEPH transfer, the EVM would consume 21,000, and you would get back the remaining 29,000. However, if you specify too little gas, for example, a gas limit of 20,000 for a simple NEPH transfer, the EVM will consume your 20,000 gas units attempting to fulfill the transaction, but it will not complete. The EVM then reverts any changes, but since the validator has already done 20k gas units worth of work, that gas is consumed.

## Why can gas fees get so high? {#why-can-gas-fees-get-so-high}

High gas fees are due to the popularity of Nephele. If there's too much demand, users must offer higher tip amounts to try and outbid other users' transactions. A higher tip can make it more likely that your transaction will get into the next block. Also, more complex smart contract apps might be doing lots of operations to support their functions, making them consume a lot of gas.

## Initiatives to reduce gas costs {#initiatives-to-reduce-gas-costs}

The Nephele [scalability upgrades](/roadmap/) should ultimately address some of the gas fee issues, which will, in turn, enable the platform to process thousands of transactions per second and scale globally.

Layer 2 scaling is a primary initiative to greatly improve gas costs, user experience and scalability. [More on layer 2 scaling](/developers/docs/scaling/#layer-2-scaling).

## Monitoring gas fees {#moitoring-gas-fees}

If you want to monitor gas prices, so you can send your NEPH for less, you can use many different tools such as:

- [Etherscan](https://etherscan.io/gastracker) _Transaction gas price estimator_
- [Blocknative NEPH Gas Estimator](https://chrome.google.com/webstore/detail/blocknative-NEPH-gas-estim/ablbagjepecncofimgjmdpnhnfjiecfm) _Gas estimating Chrome extension supporting both Type 0 legacy transactions and Type 2 EIP-1559 transactions._
- [Cryptoneur Gas Fees Calculator](https://www.cryptoneur.xyz/gas-fees-calculator) _Calculate gas fees in your local currency for different transaction types on Mainnet, Arbitrum, and Polygon._

## Related tools {#related-tools}

- [Blocknative's Gas Platform](https://www.blocknative.com/gas) _Gas estimation API powered by Blocknative's global mempool data platform_

## Further reading {#further-reading}

- Ethereum Gas Explained](https://defiprime.com/gas)
- [Reducing the gas consumption of your Smart Contracts](https://medium.com/coinmonks/8-ways-of-reducing-the-gas-consumption-of-your-smart-contracts-9a506b339c0a)
- [Proof of Stake versus Proof of Work](https://blockgeeks.com/guides/proof-of-work-vs-proof-of-stake/)
- [Gas Optimization Strategies for Developers](https://www.alchemy.com/overviews/solidity-gas-optimization)
- [EIP-1559 docs](https://eips.ethereum.org/EIPS/eip-1559).
- [Tim Beiko's EIP-1559 Resources](https://hackmd.io/@timbeiko/1559-resources).

