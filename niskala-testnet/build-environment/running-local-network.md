# Running Local Network

This section is focused on guiding users through the process of setting up and running a local network, with clear steps and additional context to ensure a smooth setup experience.

***

## Setting Up a Local Network with Niskala

This guide provides detailed instructions for setting up and running a local network using Niskala, built with Substrate. This setup is ideal for development, testing, and experimentation with Niskala.

### Prerequisites

Before you begin, ensure you have the following:

* A compatible operating system (Linux, macOS, or Windows).
* [Rust](https://www.rust-lang.org/tools/install) installed on your system.
* Familiarity with command-line operations.
* [Zombienet](https://github.com/paritytech/zombienet) installed for local testnet setup.
* Get the Latest Binary, visit the Release page of the [Mandala Github repository.](https://github.com/MandalaChain/Mandala-Node/tree/main)

### Installation

#### Step 1: Install Dependencies

Ensure your system has the necessary dependencies. Follow the [Substrate Installation Guide](https://docs.substrate.io/install/) for your specific platform to install required packages.

#### Step 2: Clone the Repository

Clone the Mandala Node repository to your local machine:

```sh
git clone https://github.com/your-repo/mandala-node.git
cd mandala-node
```

#### Step 3: Build the Node

Compile the node with the desired runtime:

```sh
cargo build --release --features mandala-native
```

> **Note:** Use `niskala-native` if you prefer the Niskala runtime.

### Running a Local Network

#### Step 1: Generate Genesis State and Runtime

Generate the genesis state and runtime for your node:

```bash
./target/release/mandala export-genesis-state --dev > <path>
```

```bash
./target/release/mandala export-genesis-wasm --dev > <path>
```

> Replace the path with folder you wish to store the state and runtime

#### Step 2: Set Up the Relay Chain

Navigate to your Zombienet directory and start the relay chain:

```bash
cd zombienet
./run.sh <zombienet-path>
```

> **Info:** This command initializes a 2-node relay chain with Bob and Alice as validators.

#### Step 3: Launch the Collator

Return to the Mandala Node directory and start the collator:

```bash
./target/release/mandala --dev --charlie --collator --rpc-port 9944 --port 30333 -- --chain ./zombienet/plain.json --discover-local --port 30334
```

#### Step 4: Register the Parachain

After starting the Zombienet script, register your parachain:

1. Open a browser and navigate to the [Polkadot/Substrate Portal](https://polkadot.js.org/apps/#/explorer?rpc=ws://localhost:9944).
2. In the developer tab, go to "sudo" and select `parasSudoWrapper`.
3. Choose `sudoScheduleParaInitialize(id, genesis)`.
4. Set the `id` parameter to `2000`.
5. Upload the `genesis-state` file for the `genesisHead` parameter.
6. Set `paraKind` to `true` and submit the transaction.

Wait for the next epoch to start, and your parachain should begin producing blocks.

### Interacting with the Local Network

You can interact with your local network using the [Polkadot/Substrate Portal](https://polkadot.js.org/apps/#/explorer?rpc=ws://localhost:9944). This interface allows you to explore blocks, transactions, and other network activities.

***

### Additional Resources

* [Substrate Documentation](https://docs.substrate.io/)
* [Polkadot-JS Apps](https://github.com/polkadot-js/apps)
