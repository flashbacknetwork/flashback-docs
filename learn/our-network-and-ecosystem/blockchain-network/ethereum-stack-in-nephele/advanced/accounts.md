# Smart Contract Accounts

Traditionally, Nephele users rely on EOA that use private keys for transactions and interactions. These accounts often face issues with security, user experience, and flexibility, especially for newcomers unfamiliar with the intricacies of blockchain technology.

## ERC-4337 Standard <a href="#contract-accounts" id="contract-accounts"></a>

ERC-4337 seeks to transform this by implementing accounts that operate more like smart contracts—these are called smart contract accounts or smart accounts. This shift enables several innovative features and benefits:

1. <mark style="color:purple;">**Enhanced Security and Control:**</mark> Smart contract accounts can use various signature types beyond the traditional private key. They can incorporate biometrics, social logins, and multi-signature setups, offering more security and flexibility for transactions​.
2. <mark style="color:purple;">**User-Friendly Features:**</mark> These accounts allow for more intuitive interactions similar to traditional online banking experiences. Users can manage transaction fees in different tokens, potentially even using ERC-20 tokens for gas payments, simplifying the process for those holding a variety of digital assets​.
3. <mark style="color:purple;">**Streamlined Operations:**</mark> Account Abstraction allows for the batching of multiple operations into a single transaction. This simplifies processes that would typically require multiple steps, such as token swaps on decentralized exchanges​.
4. <mark style="color:purple;">**Gas Sponsorships and Gasless Transactions:**</mark> This is a particularly intriguing use case where transaction fees can be sponsored by third parties, which could lead to new business models and incentives within platforms​.
5. <mark style="color:purple;">**Decentralized Operation without Consensus Layer Changes:**</mark> ERC-4337 operates without requiring changes to the consensus protocol, facilitating easier and quicker adoption. It uses a system of pseudo-transactions that are bundled and processed by entities called bundlers, streamlining the process without altering the core network operations​.

In essence, ERC-4337's account abstraction makes blockchain interactions more secure, user-friendly, and adaptable, potentially accelerating broader adoption of blockchain technology by alleviating many of the traditional barriers faced by users. For developers and users alike, this represents a major leap forward in making blockchain technology more accessible and practical for everyday use and new applications.

## The Fields in a Smart Contract Account <a href="#an-account-examined" id="an-account-examined"></a>

The smart contract account supports the two fiels of the EOA (see here). Two additional fields are added to the account:

* `codeHash` – This hash refers to the _code_ of an account on the Ethereum virtual machine (EVM) inherited in Nehphele. Contract accounts have code fragments programmed in that can perform different operations. This EVM code gets executed if the account gets a message call. It cannot be changed, unlike the other account fields. All such code fragments are contained in the state database under their corresponding hashes for later retrieval. This hash value is known as a codeHash. For externally owned accounts, the codeHash field is the hash of an empty string (EOA).
* `storageRoot` – Sometimes known as a storage hash. A 256-bit hash of the root node of a Merkle Patricia trie that encodes the storage contents of the account (a mapping between 256-bit integer values), encoded into the trie as a mapping from the Keccak 256-bit hash of the 256-bit integer keys to the RLP-encoded 256-bit integer values. This trie encodes the hash of the storage contents of this account, and is empty by default (EOA).
