# Account

Niskala is an Ethereum-compatible blockchain network that operates within the Polkadot ecosystem. Niskala replaces the default Substrate-style accounts and keys with Ethereum-style accounts and keys. This compatibility allows users to interact with their Niskala accounts using MetaMask and other Ethereum tools.

Additionally, Niskala supports interaction through Polkadot.js Apps, which natively handle H160 addresses and ECDSA keys. This dual compatibility provides flexibility and ease of use for developers and users alike.

### Substrate EVM Compatible Blockchain

Niskala, as a Substrate-based blockchain, can offer a full EVM implementation. This capability allows for the execution of Solidity-based smart contracts with minimal to no changes. By integrating the EVM pallet into its runtime, Niskala supports EVM functionality, while the Ethereum Pallet with Frontier ensures Ethereum RPC compatibility. This setup enables Niskala to offer Ethereum compatibility, similar to other parachains in the Polkadot ecosystem.

#### Address Mapping

In this configuration, users have Ethereum-style addresses (H160 format) on a Substrate-based chain. These addresses are 42-character hexadecimal strings, including the "0x" prefix, and are linked to private keys used for signing transactions on the Ethereum side of the chain. However, these addresses are mapped to Substrate-style addresses (H256 format) within the Substrate Balance pallet.

A user, such as Alice, only knows the private key of her H160 address and not the mapped H256 version. Consequently, she can perform read-only operations through Substrate’s API but cannot send transactions with her H256 address. To fully operate on the Substrate side of the chain, including staking, balances, and governance, Alice needs a separate H256 address with a different private key.

### Niskala Unified Accounts

Niskala aims to establish a fully Ethereum-compatible environment within the Polkadot ecosystem, prioritizing an exceptional user experience. This commitment goes beyond the fundamental features of Ethereum, incorporating additional functionalities such as on-chain governance, staking, and cross-chain integrations.

With the unified account system, users, like Bob, only need one H160 address and its associated private key to perform all the aforementioned tasks, encompassing both EVM and Substrate operations.

In this new configuration, Bob retains just one private key linked to a single address. He no longer needs to transfer balances between multiple accounts and can access all features using this one account and private key. This single account has been standardized to align with Ethereum's H160 address format and ECDSA key standards.
