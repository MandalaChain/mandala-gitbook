# Account

## Mandala Chain Account

### Address Format

The address format used in Substrate-based chains like Mandala Chain is SS58. SS58 is a modification of Base-58-check from Bitcoin with some minor modifications. Notably, the format contains an address type prefix that identifies an address as belonging to a specific network. Mandala Chain supports EVM as well as WASM smart contract. With the use of two different virtual machines come two different kinds of addresses.

* A Mandala Chain Native address or SS58 address
* A Mandala Chain EVM address or H160 address which starts with 0x

You will interact with our Mandala Chain native address when using WASM dApps. Using this address requires extensions. We recommend using the Mandala Wallet or Polkadot JS extension. We will support EVM-based wallets in the future.
