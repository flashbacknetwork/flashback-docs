# Blocks

Blocks are batches of transactions with a hash of the previous block in the chain. This links blocks together (in a chain) because hashes are cryptographically derived from the block data. This prevents fraud, because one change in any block in history would invalidate all the following blocks as all subsequent hashes would change and everyone running the blockchain would notice.

## What is a Block? <a href="#why-blocks" id="why-blocks"></a>

To ensure that all participants on the Nephele and Ethereum networks maintain a synchronized state and agree on the precise history of transactions, we batch transactions into blocks. This means dozens (or hundreds) of transactions are committed, agreed on, and synchronized all at once.

By spacing out commits, we give all network participants enough time to come to consensus: even though transaction requests occur dozens of times per second, blocks are only created and committed once every twelve seconds.

## How Blocks Work <a href="#how-blocks-work" id="how-blocks-work"></a>

To preserve the transaction history, blocks are strictly ordered (every new block created contains a reference to its parent block), and transactions within blocks are strictly ordered as well. Except in rare cases, at any given time, all participants on the network agree on the exact number and history of blocks and work to batch the current live transaction requests into the next block.

Once a block is put together by a randomly selected validator on the network, it is propagated to the rest of the network; all nodes add this block to the end of their blockchain, and a new validator is selected to create the next block. The exact block-assembly process and commitment/consensus process is currently specified by Ethereum’s “proof-of-stake” protocol.

## Content of a Block <a href="#block-anatomy" id="block-anatomy"></a>

There is a lot of information contained within a block. At the highest level a block contains the following fields:

| Field            | Description                                           |
| ---------------- | ----------------------------------------------------- |
| `slot`           | the slot the block belongs to                         |
| `proposer_index` | the ID of the validator proposing the block           |
| `parent_root`    | the hash of the preceding block                       |
| `state_root`     | the root hash of the state object                     |
| `body`           | an object containing several fields, as defined below |

The block `body` contains several fields of its own:

| Field                | Description                                        |
| -------------------- | -------------------------------------------------- |
| `randao_reveal`      | a value used to select the next block proposer     |
| `eth1_data`          | information about the deposit contract             |
| `graffiti`           | arbitrary data used to tag blocks                  |
| `proposer_slashings` | list of validators to be slashed                   |
| `attester_slashings` | list of attesters to be slashed                    |
| `attestations`       | list of attestations in favor of the current block |
| `deposits`           | list of new deposits to the deposit contract       |
| `voluntary_exits`    | list of validators exiting the network             |
| `sync_aggregate`     | subset of validators used to serve light clients   |
| `execution_payload`  | transactions passed from the execution client      |

The `attestations` (see [here](../validators/attestations.md)) field contains a list of all the attestations in the block. Attestations have their own data type that contains several pieces of data. Each attestation contains:

| Field              | Description                                                 |
| ------------------ | ----------------------------------------------------------- |
| `aggregation_bits` | a list of which validators participated in this attestation |
| `data`             | a container with multiple subfields                         |
| `signature`        | aggregate signature of all attesting validators             |

The `data` field in the `attestation` contains the following:

| Field               | Description                                              |
| ------------------- | -------------------------------------------------------- |
| `slot`              | the slot the attestation relates to                      |
| `index`             | indices for attesting validators                         |
| `beacon_block_root` | the root hash of the Beacon block containing this object |
| `source`            | the last justified checkpoint                            |
| `target`            | the latest epoch boundary block                          |

Executing the transactions in the `execution_payload` updates the global state. All clients re-execute the transactions in the `execution_payload` to ensure the new state matches that in the new block `state_root` field. This is how clients can tell that a new block is valid and safe to add to their blockchain. The `execution payload` itself is an object with several fields. There is also an `execution_payload_header` that contains important summary information about the execution data. These data structures are organized as follows:

The `execution_payload_header` contains the following fields:

| Field               | Description                                                         |
| ------------------- | ------------------------------------------------------------------- |
| `parent_hash`       | hash of the parent block                                            |
| `fee_recipient`     | account address for paying transaction fees to                      |
| `state_root`        | root hash for the global state after applying changes in this block |
| `receipts_root`     | hash of the transaction receipts trie                               |
| `logs_bloom`        | data structure containing event logs                                |
| `prev_randao`       | value used in random validator selection                            |
| `block_number`      | the number of the current block                                     |
| `gas_limit`         | maximum gas allowed in this block                                   |
| `gas_used`          | the actual amount of gas used in this block                         |
| `timestamp`         | the block time                                                      |
| `extra_data`        | arbitrary additional data as raw bytes                              |
| `base_fee_per_gas`  | the base fee value                                                  |
| `block_hash`        | Hash of execution block                                             |
| `transactions_root` | root hash of the transactions in the payload                        |
| `withdrawal_root`   | root hash of the withdrawals in the payload                         |

The `execution_payload` itself contains the following (notice this is identical to the header except that instead of the root hash of the transactions it includes the actual list of transactions and withdrawal information) :

| Field              | Description                                                         |
| ------------------ | ------------------------------------------------------------------- |
| `parent_hash`      | hash of the parent block                                            |
| `fee_recipient`    | account address for paying transaction fees to                      |
| `state_root`       | root hash for the global state after applying changes in this block |
| `receipts_root`    | hash of the transaction receipts trie                               |
| `logs_bloom`       | data structure containing event logs                                |
| `prev_randao`      | value used in random validator selection                            |
| `block_number`     | the number of the current block                                     |
| `gas_limit`        | maximum gas allowed in this block                                   |
| `gas_used`         | the actual amount of gas used in this block                         |
| `timestamp`        | the block time                                                      |
| `extra_data`       | arbitrary additional data as raw bytes                              |
| `base_fee_per_gas` | the base fee value                                                  |
| `block_hash`       | Hash of execution block                                             |
| `transactions`     | list of transactions to be executed                                 |
| `withdrawals`      | list of withdrawal objects                                          |

The `withdrawals` list contains `withdrawal` objects structured in the following way:

| Field            | Description                        |
| ---------------- | ---------------------------------- |
| `address`        | account address that has withdrawn |
| `amount`         | withdrawal amount                  |
| `index`          | withdrawal index value             |
| `validatorIndex` | validator index value              |

## Block Time <a href="#block-time" id="block-time"></a>

Block time refers to the time separating blocks proposed by the blockchain validators. In Nephele and Ethereum, time is divided up into twelve second units called 'slots'. In each slot a single validator is selected to propose a block. Assuming all validators are online and fully functional, there will be a block in every slot, meaning the block time is 12s. However, occasionally validators might be offline when called to propose a block, meaning slots can sometimes go empty.

## Block Size <a href="#block-size" id="block-size"></a>

A final important note is that blocks themselves are bounded in size. Each block has a target size of 15 million gas but the size of blocks will increase or decrease following network demands, up until the block limit of 30 million gas (2x target block size). The block gas limit can be adjusted upwards or downwards by a factor of 1/1024 from the previous block's gas limit.

As a result, validators can change the block gas limit through consensus. The total amount of gas expended by all transactions in the block must be less than the block gas limit. This is important because it ensures that blocks can’t be arbitrarily large. If blocks could be arbitrarily large, then less performant full nodes would gradually stop being able to keep up with the network due to space and speed requirements. The larger the block, the greater the computing power required to process them in time for the next slot. This is a centralizing force, which is resisted by capping block sizes.

***

## The Size growth by Adding Blocks

The growth rate of the Ethereum blockchain, in terms of its size in gigabytes (GB), is significant due to the increasing number of transactions, smart contracts, and dApps deployed on the network. Below, I'll provide an overview of the Ethereum blockchain size growth over several time periods from 2014 to 2024. Note that the data is based on full nodes (which store the entire blockchain history).

#### 1. **2014 to 2016**

* Ethereum was launched in July 2015.
* By the end of 2015, the blockchain size was around **5 GB**.
* By the end of 2016, the size grew to approximately **25 GB**.
* **Growth Rate:** The blockchain grew by about **20 GB** over these two years.

#### 2. **2016 to 2018**

* By early 2017, the blockchain size had reached **35 GB**.
* By the end of 2017, it was approximately **150 GB** due to the ICO boom.
* By the end of 2018, the size had reached around **200 GB**.
* **Growth Rate:** The blockchain size increased by about **175 GB** during this period.

#### 3. **2018 to 2020**

* At the start of 2019, the size was around **220 GB**.
* By the end of 2019, the size grew to around **250 GB**.
* By the end of 2020, the blockchain size was approximately **400 GB**.
* **Growth Rate:** The size grew by about **180 GB** over these two years.

#### 4. **2020 to 2022**

* By the beginning of 2021, the blockchain size reached about **450 GB**.
* By the end of 2021, it grew to around **800 GB** due to the rise in DeFi and NFTs.
* By the end of 2022, the size had reached around **1.2 TB (1200 GB)**.
* **Growth Rate:** The size increased by about **750 GB** in this period.

#### 5. **2022 to 2024**

* At the start of 2023, the blockchain size was around **1.3 TB**.
* By mid-2023, the size grew to approximately **1.5 TB**.
* As of mid-2024, the size is estimated to be around **1.7 TB**.
* **Growth Rate:** The growth was about **500 GB** over these two years.

| Period    | Approximate Growth (GB) |
| --------- | ----------------------- |
| 2014-2016 | 20 GB                   |
| 2016-2018 | 175 GB                  |
| 2018-2020 | 180 GB                  |
| 2020-2022 | 750 GB                  |
| 2022-2024 | 500 GB                  |
