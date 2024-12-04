# Slashing

Slashing in the context of storage providers in blockchain networks like Filecoin serves as a penalty system for various infractions. These penalties ensure that storage providers maintain reliable uptime and adhere to network protocols. Here's a clearer explanation of the types of slashing and their implications:

## Storage Fault Slashing

Storage fault slashing encompasses several penalties that are applied when storage providers fail to meet their reliability commitments or choose to exit the network:

* **Fault Fees**: These are daily penalties incurred when a storage provider's sector fails to submit the required Proofs-of-Spacetime, proving that data is being correctly stored. These fees accumulate daily until the provider's associated wallet is depleted, leading to their removal from the network.
* **Sector Penalties**: If a sector is found to be faulty during a WindowPoSt (Windowed Proof of Spacetime) check and was not previously declared as such, a sector penalty is imposed in addition to the ongoing fault fees. This penalty is applied immediately after the fault is identified.
* **Termination Fees**: These fees are charged when a sector is either voluntarily or involuntarily terminated from the network. This could be due to various reasons, including the provider's decision to exit or compliance failures.

## Consensus Fault Slashing

Consensus fault slashing targets storage providers that maliciously attack the network's consensus mechanisms. This type of slashing penalizes actions that compromise the network's integrity, such as double-spending or mining malicious blocks.

* **Penalty Application**: This penalty is severe and can result in significant financial loss for the provider, acting as a strong deterrent against malicious activities that threaten network security.

These mechanisms are crucial for maintaining the integrity and reliability of the storage network, ensuring that providers adhere to agreed-upon service levels and network rules. Slashing not only discourages undesirable behaviors but also helps to stabilize the network by removing unreliable or malicious actors.
