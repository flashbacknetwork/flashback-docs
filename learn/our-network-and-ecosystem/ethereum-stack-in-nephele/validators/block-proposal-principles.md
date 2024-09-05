# Block Proposals

Blocks are the fundamental units of the blockchain. They are discrete information units passed between nodes, agreed upon, and added to each node's database. This page explains how blocks are produced and proposed to the network.

## A Gentle Reminder <a href="#who-produces-blocks" id="who-produces-blocks"></a>

Validator accounts propose blocks. Validator accounts are managed by node operators who run validator software as part of their execution and consensus clients. They have deposited at least 32 ETH in Ethereum into the deposit contract. However, each validator is only occasionally responsible for proposing a block. Ethereum measures time in slots and epochs. Each slot is twelve seconds, and 32 slots (6.4 minutes) make up an epoch. Every slot is an opportunity to add a new block on Ethereum.

## Random selection of Validators <a href="#random-selection" id="random-selection"></a>

A single validator is pseudo-randomly chosen to propose a block in each slot. There is no such thing as true randomness in a blockchain because if each node generated genuinely random numbers, they couldn't reach a consensus. Instead, the aim is to make the validator selection process unpredictable. The randomness uses an algorithm called [RANDAO ](https://inevitableeth.com/home/ethereum/network/consensus/randao)that mixes a hash from the block proposer with a seed (random number) that gets updated every block. This value selects a specific validator from the total validator set. The validator selection is fixed two epochs in advance to protect against certain kinds of seed prediction and manipulation.

Although validators add to RANDAO in each slot, the global RANDAO value is only updated once per epoch (32 slots). To compute the index of the next block proposer, the RANDAO value is mixed with the slot number to give a unique value in each slot. An individual validator's selection probability is not simply `1/N` (where `N` = total active validators). Instead, it is weighted by the effective token balance of each validator. In Ethereum, the maximum effective balance is 32 ETH (this means that `balance < 32 ETH` leads to a lower weight than `balance == 32 ETH`, but `balance > 32 ETH` does not lead to higher weighting than `balance == 32 ETH`).

Only one block proposer is selected in each slot. Under normal conditions, a single block producer creates and releases a single block in their dedicated slot. Creating two blocks for the same slot is a slashable offense, often called "equivocation."

## How is the Block Created? <a href="#how-is-a-block-created" id="how-is-a-block-created"></a>

The block proposer is expected to broadcast a signed beacon block that builds on top of the most recent head of the chain according to the view of their locally-run fork choice algorithm. The fork choice algorithm applies any queued attestations left over from the previous slot and then finds the block with the greatest accumulated weight of attestations in its history. That block is the parent of the new block created by the proposer.

The block proposer creates a block by collecting data from its local database and view of the chain. The contents of the block are shown in the snippet below:

```
1class BeaconBlockBody(Container):2    randao_reveal: BLSSignature3    eth1_data: Eth1Data4    graffiti: Bytes325    proposer_slashings: List[ProposerSlashing, MAX_PROPOSER_SLASHINGS]6    attester_slashings: List[AttesterSlashing, MAX_ATTESTER_SLASHINGS]7    attestations: List[Attestation, MAX_ATTESTATIONS]8    deposits: List[Deposit, MAX_DEPOSITS]9    voluntary_exits: List[SignedVoluntaryExit, MAX_VOLUNTARY_EXITS]10    sync_aggregate: SyncAggregate11    execution_payload: ExecutionPayloadShow all
```

Here is the list of the different values of block (you can find more details [here](../basics/blocks.md)):

* `randao_reveal` field takes a verifiable random value that the block proposer creates by signing the current epoch number.
* `eth1_data` is a vote for the block proposer's view of the deposit contract, including the root of the deposit [Merkle trie](https://ethereum.org/en/developers/docs/data-structures-and-encoding/patricia-merkle-trie/) and the total number of deposits that enable new deposits to be verified.
* `graffiti` is an optional field that can add a message to the block.
* `proposer_slashings` and `attester_slashings` contain proof that specific validators have committed slashable offenses according to the proposer's view of the chain.
* `deposits` is a list of new validator deposits that the block proposer is aware of, and
* `voluntary_exits` is a list of validators that wish to exit that the block proposer has heard about on the consensus layer gossip network.
* `sync_aggregate` is a vector showing which validators were previously assigned to a sync committee (a subset of validators that serve light client data) and participated in signing data.
* `execution_payload` enables information about transactions between the execution and consensus clients. The `execution_payload` is a block of execution data that gets nested inside a beacon block. The fields inside the `execution_payload` reflect the block structure outlined in the Ethereum yellow paper, except that there are no comments, and `prev_randao` exists in place of `difficulty`. The execution client has access to a local pool of transactions that it has heard about on its own gossip network. These transactions are executed locally to generate an updated state trie called a post-state. The transactions are included in the `execution_payload` as a list called `transactions` and the post-state is provided in the `state-root` field.

All of these data are collected in a beacon block, signed, and broadcast to the block proposer's peers, who propagate it onto their peers, etc.

## What happens during the Proposal? <a href="#what-happens-to-blocks" id="what-happens-to-blocks"></a>

The block is added to the block proposer's local database and broadcast to peers over the consensus layer gossip network. When a validator receives the block, it verifies the data inside it, including checking that the block has the correct parent, corresponds to the correct slot, that the proposer index is the expected one, that the RANDAO reveals is valid, and that the proposer is not slashed. The `execution_payload` is unbundled, and the validator's execution client re-executes the transactions in the list to check the proposed state change. Assuming the block passes all these checks, each validator adds the block to its canonical chain. The process then starts again in the next slot.
