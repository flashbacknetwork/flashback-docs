# Gas Fees

To help you better understand this page, we recommend you first read [externally-owned accounts (EOA)](accounts.md) and our [introduction](../../../../introduction/) about Nephele.

***

Gas is a unit that measures the computational effort required to execute operations on the Nephele network. Each transaction on Nephele requires a certain amount of computational resources, which must be compensated to prevent the network from being overloaded by spam or getting stuck in infinite loops.

The cost of these computations is covered by gas fees. The gas fee for a transaction is calculated by multiplying the amount of gas needed for the operation by the cost per unit of gas. Importantly, this fee is charged whether the transaction succeeds or fails, ensuring that resources used in processing the transaction are accounted for.

Gas fees are essential for maintaining the health and efficiency of the Nephele network. They incentivize miners to process transactions and secure the network, while also deterring malicious actors from abusing the system.

The gas fee is **the amount of gas used to do some operation, multiplied by the cost per unit gas**. The fee is paid regardless of whether a transaction succeeds or fails.

![A diagram showing where gas is needed in EVM operations](gas.png)

Gas fees have to be paid with the cryptocurrency of the blockchain network. Gas prices are usually quoted in gwei, a denomination of NEPH. Each gwei is equal to one-billionth of an NEPH (0.000000001 NEPH or 10-9 NEPH). Instead of saying that your gas costs 0.000000001 Nephele, you can say your gas costs 1 gwei.

The word 'gwei' is a contraction of 'giga-wei', meaning 'billion wei'. One gwei is equal to one billion wei. Wei itself (named after [Wei Dai](https://wikipedia.org/wiki/Wei\_Dai), creator of [b-money](https://www.investopedia.com/terms/b/bmoney.asp)) is the smallest unit of NEPH.

## What is a gas made of? <a href="#how-are-gas-fees-calculated" id="how-are-gas-fees-calculated"></a>

A transaction must spend gas to the network to integrate it into the EVM's submission and validation transaction procedure. The transaction operator can customize the gas, which will play on how the validators will prioritize the event. The higher is the gas fees; the higher is the commitment of validators to prioritize the transaction.

The total gas is divided into the <mark style="color:yellow;">base fee</mark> and the <mark style="color:yellow;">priority fee.</mark>&#x20;

### Base fee <a href="#base-fee" id="base-fee"></a>

Every block has a base fee that acts as a reserve price. To be eligible for inclusion in a block, the offered price per gas must at least equal the base fee. The base fee is calculated independently of the current block and is instead determined by the blocks before it, making transaction fees more predictable for users. When the block is created, this base fee is "burned," removing it from circulation.&#x20;

The base fee is calculated by a formula that compares the size of the previous block (the amount of gas used for all the transactions) with the target size. If the target block size is exceeded, the base fee will increase by a maximum of 12.5% per block. This exponential growth makes it economically non-viable for block size to remain high indefinitely.

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

### Priority fee (tips) <a href="#priority-fee" id="priority-fee"></a>

The priority fee (tip) incentivizes validators to include a transaction in the block. Without tips, validators would find it economically viable to mine empty blocks, as they would receive the same block reward. Small tips give validators a minimal incentive to include a transaction. For transactions to be preferentially executed ahead of other transactions in the same block, a higher tip can be added to try to outbid competing transactions.

## How to calculating gas fees in practice <a href="#calculating-fees-in-practice" id="calculating-fees-in-practice"></a>

Let's say Jordan has to pay Taylor 1 NEPH. A NEPH transfer requires 21,000 units of gas, and the base fee is 10 gwei. Jordan includes a tip of 2 gwei.

The total fee would now be equal to:

`total_fee = units of gas used * (base fee + priority fee)`

i.e. `21,000 * (10 + 2) = 252,000 gwei` (0.000252 NEPH).

When Jordan sends the money, 1.000252 NEPH will be deducted from Jordan's account. Taylor will be credited 1.0000 NEPH. The validator receives the tip of 0.000042 NEPH. The `base fee` of 0.00021 NEPH is burned.

You can explicitly state how much you will pay in priority fee. However, most wallet providers will automatically set a recommended transaction fee (base fee + recommended priority fee) to reduce the amount of complexity burdened onto their users.

## What is the gas limit? <a href="#what-is-gas-limit" id="what-is-gas-limit"></a>

The gas limit refers to the maximum amount of gas you are willing to consume on a transaction. More complicated transactions involving [smart contracts](smart-contracts.md) require more computational work, so they require a higher gas limit than a simple payment. <mark style="color:purple;">**A standard NEPH transfer requires a gas limit of 21,000 units of gas.**</mark>

For example, if you put a gas limit of 50,000 for a simple NEPH transfer, the EVM would consume 21,000, and you would get back the remaining 29,000. However, if you specify too little gas, for example, a gas limit of 20,000 for a simple NEPH transfer, the EVM will consume your 20,000 gas units attempting to fulfill the transaction, but it will not complete. The EVM then reverts any changes, but since the validator has already done 20k gas units worth of work, that gas is consumed.

Although a transaction includes a limit, any gas not used in a transaction is returned to the user (i.e. `max fee - (base fee + tip)` is returned)

## Why can gas fees get so high? <a href="#why-can-gas-fees-get-so-high" id="why-can-gas-fees-get-so-high"></a>

High gas fees are due to the popularity of Nephele. If there's too much demand, users must offer higher tip amounts to try and outbid other users' transactions. A higher tip can make it more likely that your transaction will get into the next block. Also, more complex smart contract apps might be doing lots of operations to support their functions, making them consume a lot of gas.

## Initiatives to reduce gas costs <a href="#initiatives-to-reduce-gas-costs" id="initiatives-to-reduce-gas-costs"></a>

The Nephele [scalability upgrades](../../../../../roadmap/) should ultimately address some of the gas fee issues, which will, in turn, enable the platform to process thousands of transactions per second and scale globally.

Layer 2 scaling is a primary initiative to greatly improve gas costs, user experience and scalability. [More on layer 2 scaling](../../../../../developers/docs/scaling/#layer-2-scaling).

## Monitoring gas fees <a href="#moitoring-gas-fees" id="moitoring-gas-fees"></a>

If you want to monitor gas prices, so you can send your NEPH for less, you can use many different tools such as:

* [Etherscan](https://etherscan.io/gastracker) _Transaction gas price estimator_
* [Blocknative NEPH Gas Estimator](https://chrome.google.com/webstore/detail/blocknative-NEPH-gas-estim/ablbagjepecncofimgjmdpnhnfjiecfm) _Gas estimating Chrome extension supporting both Type 0 legacy transactions and Type 2 EIP-1559 transactions._
* [Cryptoneur Gas Fees Calculator](https://www.cryptoneur.xyz/gas-fees-calculator) _Calculate gas fees in your local currency for different transaction types on Mainnet, Arbitrum, and Polygon._

## Related tools <a href="#related-tools" id="related-tools"></a>

* [Blocknative's Gas Platform](https://www.blocknative.com/gas) _Gas estimation API powered by Blocknative's global mempool data platform_

## Further reading <a href="#further-reading" id="further-reading"></a>

* Ethereum Gas Explained]\(https://defiprime.com/gas)
* [Reducing the gas consumption of your Smart Contracts](https://medium.com/coinmonks/8-ways-of-reducing-the-gas-consumption-of-your-smart-contracts-9a506b339c0a)
* [Proof of Stake versus Proof of Work](https://blockgeeks.com/guides/proof-of-work-vs-proof-of-stake/)
* [Gas Optimization Strategies for Developers](https://www.alchemy.com/overviews/solidity-gas-optimization)
* [EIP-1559 docs](https://eips.ethereum.org/EIPS/eip-1559).
* [Tim Beiko's EIP-1559 Resources](https://hackmd.io/@timbeiko/1559-resources).
