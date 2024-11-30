# Quality-of-Network (QoN) Optimizer

The Quality-of-Network (QoN) Optimizer is a smart contract designed for compatible Ethereum Virtual Machine (EVM) blockchain networks. It is intended to optimize data availability and integrity through a decentralized network of validators.

This document outlines the technical specifications of the QoN Optimizer, which leverages Proofs of Spacetime (PoSt) within the Dencun data availability layer to ensure secure and efficient data transactions. The QoN Optimizer utilizes a contract-based mechanism where validators are required to store and reliably provide data upon request. Validators submit PoSt to demonstrate they have held a specific amount of data for a designated period.

The system is designed to incentivize speed and reliability among validators by providing economic rewards and penalties. Nephele is the first blockchain to leverage the PoSt for the quality of storage nodes, which is the **only truly decentralized** proof system.

## Contract Specifications

**1. User Contract Deployment**

* **Parameters**:
  * `x`: Number of validator nodes.
  * `y`: Duration for which the contract is active.
* **Parameters Initialization**: Upon deployment, the contract initializes with predefined durations of data storage for registration and operation, and contract fee corresponding to the sum of the fees for the selected validators.
* **Functionality**:
  * A user deploys the QoN Optimizer contract by specifying the desired number of validator nodes and the contract duration.
  * Validators are then able to join the contract by registering themselves and proving their capacity to store data.
* **State Variables**:
  * `registrationEndTime`: Timestamp indicating the end of the validator registration period.
  * `contractEndTime`: Timestamp when the contract ceases to accept data requests.
  * `minimumFee`: Staked amount required for a node to participate as a validator.

**2. Validator Contract Management and Duties**

* **Registration**: When a contract is submitted, validators register by sending a transaction (data collateral), including a fee. The contract records each validator’s commitment and capabilities.
* **Data Handling Responsibilities**: After registration, validators respond to data requests from users, proving delivery through cryptographic signatures linked to the off-chain PoSt verification.

**3 Data Requests**

* **Trigger**:
  * Users can request the data stored by the validators at any point during the contract duration.
* **Process**:
  * Users send a data request transaction on-chain, specifying which data they wish to access.
  * This transaction is visible to all participating validators.

**4. Validator Data Provision**

* **Data Provision and Verification**: Validators fetch the requested data and provide it back to the requester with a response time and a signature.
* **Responsibility**:
  * Upon receiving a data request, validators are required to send the requested file directly to the user.
* **Verification**:
  * Validators must ensure that the data sent is accurate and complete and adhere to the terms specified in the contract.

**5. User Proof of Space-Time (PoST) Commitment**

* **Generation**:
  * Once the user receives the file, they must generate a PoSt to verify receipt and integrity of the data.
* **Submission**:
  * The PoST is then submitted to a blob on the Dencun data availability layer.
* **Purpose**:
  * This proof serves as a verifiable claim that the user has received the data as requested.

**6. Performance-Based Reward Assessment and Distribution**

* **Criteria**:
  * Throughout the contract, the performance of validators is monitored based on the average time taken to fulfill data requests.
* **Reward Mechanism**:
  * The validator with the quickest average response time throughout the contract can receive its data storage fee and a rebate of half the remaining contract fee.
  * The validator(s) with a lower average response time throughout the contract is/are eligible for a rebate amounting to half the _**post-winner fee**_ (remaining contract fee after the winner's payment) divided by the number of validator(s).
* **Security Measure**:
  * **Half of the post-winner fee** is irrevocably burnt to prevent fraudulent behavior, such as validators exchanging files among themselves to claim rebates.

## Security Considerations

* **Proof of Spacetime**:
  * The PoSt mechanism is crucial for preventing Sybil attacks and ensuring validators hold the data they claim to manage.
* **Economic Incentives**:
  * The system discourages malicious practices and promotes genuine service provision by burning half of the post-winner fees and rewarding only the most efficient validator.
* **Data Integrity**:
  * The requirement for users to validate received data through PoSt ensures data integrity and deters validators from sending incorrect or incomplete files.
