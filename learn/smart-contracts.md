# Smart Contracts

The Mandala Chain is equipped with the functionality to support smart contracts natively, compatible with WebAssembly (_ink_!) and EVM (Solidity) smart contracts.

## The difference between developing a smart contract and a layer 1 blockchain.

### Layers of Abstraction

When you write a smart contract, you create instructions that associate with and deploy to a specific chain address.

In comparison, a runtime module (known as a _pallet_) on a layer 1 blockchain is the entire logic of a chain's state transitions (called a _state transition function_).

Smart contracts must consciously implement upgradeability, while layer 1 blockchains can swap out their code entirely through a root command or via the governance pallet.

When you build a smart contract, it will eventually be deployed to a target chain with its own environment. Layer 1 blockchains allow the developer to declare the environment of their own chain, even allowing others to write smart contracts for it.

### Gas Fees

Smart contracts must find a way to limit their own execution, or else full nodes are vulnerable to DOS attacks. An infinite loop in a smart contract, for example, could consume the computational resources of an entire chain, preventing others from using it. The halting problem shows that even with a powerful enough language, it is impossible to know ahead of time whether or not a program will ever cease execution. Some platforms, such as Bitcoin, get around this constraint by providing a very restricted scripting language. Others, such as Ethereum, "charge" the smart contract "gas" for the rights to execute their code. If a smart contract does get into a state where execution will never halt, it eventually runs out of gas, ceases execution, and any state transition that the smart contract would have made is rolled back.

Layer 1 blockchains can implement arbitrarily powerful programming languages and contain no gas notion for their native logic. This means that some functionality is easier to implement for the developer, but some constructs, such as a loop without a terminating condition, should never be implemented. Leaving certain logic, such as complex loops that could run indefinitely, to a non-smart contract layer or even trying to eliminate it is a wiser choice. Layer 1 blockchains try to be proactive, while smart contract platforms are event-driven.

The Mandala Chain and other Substrate-based blockchains typically use the _**weight-fee**_ model and **not** a _**gas-metering**_ model.
