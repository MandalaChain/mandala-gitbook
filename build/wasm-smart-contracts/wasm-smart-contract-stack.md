# WASM Smart Contract Stack

## Smart Contract Runtime Environment <a href="#smart-contract-runtime-environment" id="smart-contract-runtime-environment"></a>

Mandala Chain runtimes are based on Substrate, and both networks incorporate `pallet-contracts,`a sandboxed environment used to deploy and execute WebAssembly (WASM) smart contracts. Any language that compiles to WASM may be deployed and run on this Wasm Virtual Machine. However, the code should be compatible with the `pallet-contracts` [API](https://docs.rs/pallet-contracts/latest/pallet_contracts/api_doc/trait.Current.html).

To avoid unnecessary complexity, and writing boilerplate code, the most appropriate method of building will involve the use of an eDSL specifically targeting `pallet-contracts`, such as [ink!](https://github.com/paritytech/ink) (based on Rust), or [ask!](https://github.com/ask-lang/ask) (based on AssemblyScript), or possibly others as the ecosystem grows.

After compilation, a WASM blob can then be deployed and stored on-chain.

### Execution Engine <a href="#execution-engine" id="execution-engine"></a>

Pallet-contracts uses [wasmi](https://github.com/paritytech/wasmi) as a Wasm interpreter to execute WASM smart contract blobs. Although there is a faster JIT interpreter such as [wasmtime](https://github.com/bytecodealliance/wasmtime) available in the native runtime, smart contracts are an untrusted environment that requires a higher degree of correctness of interpretation, which makes _wasmi_ a more suitable option.

## Two-step Deployment of Contracts <a href="#two-step-deployment-of-contracts" id="two-step-deployment-of-contracts"></a>

The contract code (WASM blob), and contract address and storage are decoupled from one another, so we require two steps to deploy a new contract on-chain:

1. First, upload the Wasm contract on-chain (every contract Wasm code has a `code_hash` as an identifier).
2. Second, instantiate the contract - it will create an address and storage for that contract.
3. Anyone can instantiate a contract based on its `code_hash`.

There are several benefits of decoupling the contract code from the address/storage:

* To save space on-chain. Since a contract can have several constructors and instantiations, a redeployment will create a new instance based on the same underlying code. Think about standardized tokens, like [PSP22](https://github.com/w3f/PSPs/blob/master/PSPs/psp-22.md) & [PSP34](https://github.com/w3f/PSPs/blob/master/PSPs/psp-34.md), that will have one `code_hash` & `blob` living on-chain, and as many instantiations as needed, rather than uploading code with each new instantiation (for example, on Ethereum).
* To instantiate a new contract using code within an existing smart contract (see the delegator example), `code_hash` is all that is needed.
* Some standard contracts, such as ([PSP22](https://github.com/w3f/PSPs/blob/master/PSPs/psp-22.md) and [PSP34](https://github.com/w3f/PSPs/blob/master/PSPs/psp-34.md)) will only be uploaded on-chain once, preventing users from having to pay gas costs for uploading new code.
* Update contract code for an address: replace the contract code at the specified address with a new code (see [set\_code\_hash](https://docs.rs/ink_env/4.0.0-rc/ink_env/fn.set_code_hash.html)). Storage and balances will be preserved.

### For More Information About `pallet-contracts`[​](https://docs.astar.network/docs/build/wasm/smart-contract-wasm#for-more-information-about-pallet-contracts) <a href="#for-more-information-about-pallet-contracts" id="for-more-information-about-pallet-contracts"></a>

* [`pallet-contracts` in Rust docs](https://docs.rs/pallet-contracts/14.0.0/pallet_contracts/index.html)
* [`pallet-contracts` on Github](https://github.com/paritytech/substrate/tree/master/frame/contracts)

## Client APIs <a href="#client-apis" id="client-apis"></a>

The only library available to communicate with smart contracts is [Polkadot.js API](https://github.com/polkadot-js/api).



> INFO
>
> This API provides application developers the ability to query a node and interact with the Polkadot or Substrate chains using Javascript.

Parity also developed a web application to interact with contracts called [contracts-ui](https://github.com/paritytech/contracts-ui).

## The Wasm Stack vs. Ethereum <a href="#the-wasm-stack-vs-ethereum" id="the-wasm-stack-vs-ethereum"></a>



<table><thead><tr><th width="238.33333333333331"></th><th>Ethereum</th><th>Mandala Chain</th></tr></thead><tbody><tr><td>L1 Architecture</td><td><a href="https://ethereum.org/en/developers/docs/nodes-and-clients/">Ethereum clients</a></td><td><a href="https://substrate.io/">Substrate</a> (will support EVM)</td></tr><tr><td>Smart Contract Runtime Environment</td><td><a href="https://ethereum.org/en/developers/docs/evm/">EVM</a></td><td>WASM <a href="https://github.com/paritytech/substrate/tree/master/frame/contracts">pallet-contract</a> + EVM <a href="https://github.com/paritytech/frontier">frontier</a></td></tr><tr><td>Gas Model</td><td><a href="https://ethereum.github.io/yellowpaper/paper.pdf">fixed price per instruction</a></td><td><a href="https://docs.substrate.io/reference/how-to-guides/weights/">weight</a> + <a href="https://github.com/paritytech/substrate/blob/c00ed052e7cd72cfc4bc0e00e38722081b789ff5/frame/contracts/src/lib.rs#L351">storage fees</a> + <a href="https://github.com/paritytech/substrate/blob/97ae6be11b0132224a05634c508417f048894670/frame/contracts/src/lib.rs#L331-L350">loading fees</a></td></tr><tr><td>Smart Contract DSLs</td><td>Solidity and Vyper</td><td><a href="https://github.com/paritytech/ink">ink!</a> (Rust), <a href="https://github.com/ask-lang/ask">ask!</a> (AssemblyScript), Solidity, and Vyper</td></tr><tr><td>Standards</td><td><a href="https://eips.ethereum.org/">EIPs</a></td><td><a href="https://github.com/w3f/PSPs">PSPs</a> and <a href="https://eips.ethereum.org/">EIPs</a></td></tr></tbody></table>

