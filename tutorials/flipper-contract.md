# Flipper Contract

This is step-by-step explanation of the process behind building an ink! smart contract, using a simple app called Flipper. The examples provided within this guide will help you develop an understanding of the basic elements and structure of ink! smart contracts.

### What is Flipper?[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#what-is-flipper) <a href="#what-is-flipper" id="what-is-flipper"></a>

Flipper is a basic smart contract that allows the user to toggle a boolean value located in storage to either `true` or `false`. When the flip function is called, the value will change from one to the other.

### Prerequisites[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#prerequisites) <a href="#prerequisites" id="prerequisites"></a>

Please refer to the [previous section](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/) for the list of prerequisites.

### Flipper Smart Contract[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#flipper-smart-contract) <a href="#flipper-smart-contract" id="flipper-smart-contract"></a>

In a new project folder, execute the following:

```
$ cargo contract new flipper # flipper is introduced from the beginning.
```

```
$ cd flipper/
$ cargo contract build #build flipper app
```

💡 If you receive an error such as:

```
ERROR: cargo-contract cannot build using the "stable" channel. Switch to nightly.
```

Execute:

```
$ rustup default nightly
```

to reconfigure the default Rust toolchain to use the nightly build, or

```
$ cargo +nightly contract build
```

to use the nightly build explicitly, which may be appropriate for developers working exclusively with ink!

Once the operation has finished and the Flipper project environment has been initialized, we can perform an examination of the file and folder structure. Let’s dive a bit deeper into the project structure:

#### The File Structure of Flipper[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#the-file-structure-of-flipper) <a href="#the-file-structure-of-flipper" id="the-file-structure-of-flipper"></a>

* `target`: Contains build / binary information.
* `Cargo.lock`: The lock file for the dependency package.
* `Cargo.toml`: The package configuration.
* `lib.rs`: The contract logic.

#### Flipper Contract `lib.rs`[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#flipper-contract-librs) <a href="#flipper-contract-librs" id="flipper-contract-librs"></a>

```
#![cfg_attr(not(feature = "std"), no_std)]

#[ink::contract]
mod flipper {

    /// Defines the storage of your contract.
    /// Add new fields to the below struct in order
    /// to add new static storage fields to your contract.
    #[ink(storage)]
    pub struct Flipper {
        /// Stores a single `bool` value on the storage.
        value: bool,
    }

    impl Flipper {
        /// Constructor that initializes the `bool` value to the given `init_value`.
        #[ink(constructor)]
        pub fn new(init_value: bool) -> Self {
            Self { value: init_value }
        }

        /// Constructor that initializes the `bool` value to `false`.
        ///
        /// Constructors can delegate to other constructors.
        #[ink(constructor)]
        pub fn default() -> Self {
            Self::new(Default::default())
        }

        /// A message that can be called on instantiated contracts.
        /// This one flips the value of the stored `bool` from `true`
        /// to `false` and vice versa.
        #[ink(message)]
        pub fn flip(&mut self) {
            self.value = !self.value;
        }

        /// Simply returns the current value of our `bool`.
        #[ink(message)]
        pub fn get(&self) -> bool {
            self.value
        }
    }

    /// Unit tests in Rust are normally defined within such a `#[cfg(test)]`
    /// module and test functions are marked with a `#[test]` attribute.
    /// The below code is technically just normal Rust code.
    #[cfg(test)]
    mod tests {
        /// Imports all the definitions from the outer scope so we can use them here.
        use super::*;

        /// We test if the default constructor does its job.
        #[ink::test]
        fn default_works() {
            let flipper = Flipper::default();
            assert_eq!(flipper.get(), false);
        }

        /// We test a simple use case of our contract.
        #[ink::test]
        fn it_works() {
            let mut flipper = Flipper::new(false);
            assert_eq!(flipper.get(), false);
            flipper.flip();
            assert_eq!(flipper.get(), true);
        }
    }
}
```

#### Contract Structure `lib.rs`[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#contract-structure-librs) <a href="#contract-structure-librs" id="contract-structure-librs"></a>

```
#![cfg_attr(not(feature = "std"), no_std)]

use ink_lang as ink;

#[ink::contract]
mod flipper {

        // This section defines storage for the contract.
    #[ink(storage)]
    pub struct Flipper {
    }

        // This section defines the functional logic of the contract.
    impl Flipper {
    }

        // This section is used for testing, in order to verify contract validity.
    #[cfg(test)]
    mod tests {
    }
}
```

#### Storage[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#storage) <a href="#storage" id="storage"></a>

```
    #[ink(storage)]
    pub struct Flipper {

    }
```

This annotates a struct that represents the **contract's internal state.** ([details](https://use.ink/macros-attributes/storage)):

```
#[ink(storage)]
```

Storage types:

* Rust primitives types
  * `bool`
  * `u{8,16,32,64,128}`
  * `i{8,16,32,64,128}`
  * `String`
* Substrate specific types
  * `AccountId`
  * `Balance`
  * `Hash`
* ink! storage type
  * `Mapping`
* Custom data structure [details](https://use.ink/datastructures/custom-datastructure)

This means the contract (Flipper) stores a single `bool` value in storage.

```
#[ink(storage)]
pub struct Flipper {
    value: bool,
}
```

#### Callable Functions[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#callable-functions) <a href="#callable-functions" id="callable-functions"></a>

At the time the contract is deployed, a constructor is responsible for **bootstrapping the initial state** into storage. [For more information](https://use.ink/macros-attributes/constructor).

```
#[ink(constructor)]
```

The addition of the following function will initialize `bool` to the specified `init_value`.

```
#[ink(constructor)]
pub fn new(init_value: bool) -> Self {
    Self { value: init_value }
}
```

Contracts can also contain multiple constructors. Here is a constructor that assigns a default value to `bool`. As in other languages, the default value of `bool` is `false`.

```
#[ink(constructor)]
pub fn default() -> Self {
    Self::new(Default::default())
}
```

The following will permit a function to be **publicly dispatchable**, meaning that the function can be called through a message, which is a way for contracts and external accounts to interact with the contract. Find more information [here](https://use.ink/macros-attributes/message)). Note that all public functions **must** use the `#[ink(message)]` attribute.

```
#[ink(message)]
```

The `flip` function modifies storage items, and `get` function retrieves a storage item.

```
#[ink(message)]
pub fn flip(&mut self) {
    self.value = !self.value;
}

#[ink(message)]
pub fn get(&self) -> bool {
    self.value
}
```

💡 If you are simply _reading_ from contract storage, you will only need to pass `&self`, but if you wish to _modify_ storage items, you will need to explicitly mark it as mutable `&mut self`.

```
impl Flipper {

        #[ink(constructor)]
        pub fn new(init_value: bool) -> Self {
            Self { value: init_value }
        }

        /// Constructor that initializes the `bool` value to `false`.
        ///
        /// Constructors can delegate to other constructors.
        #[ink(constructor)]
        pub fn default() -> Self {
            Self::new(Default::default())
        }

        /// A message that can be called on instantiated contracts.
        /// This one flips the value of the stored `bool` from `true`
        /// to `false` and vice versa.
        #[ink(message)]
        pub fn flip(&mut self) {
            self.value = !self.value;
        }

        /// Simply returns the current value of our `bool`.
        #[ink(message)]
        pub fn get(&self) -> bool {
            self.value
        }
    }
```

#### Test[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#test) <a href="#test" id="test"></a>

```
#[cfg(test)]
    mod tests {
        /// Imports all the definitions from the outer scope so we can use them here.
        use super::*;

        /// Imports `ink_lang` so we can use `#[ink::test]`.
        use ink_lang as ink;

        /// We test if the default constructor does its job.
        #[ink::test]
        fn default_works() {
            let flipper = Flipper::default();
            assert_eq!(flipper.get(), false);
        }

        /// We test a simple use case of our contract.
        #[ink::test]
        fn it_works() {
            let mut flipper = Flipper::new(false);
            assert_eq!(flipper.get(), false);
            flipper.flip();
            assert_eq!(flipper.get(), true);
        }
    }
```

#### Compile, Deploy, and Interact with Contracts[​](https://docs.astar.network/docs/tutorials/from-zero-to-ink-hero/flipper-contract/flipper#compile-deploy-and-interact-with-contracts) <a href="#compile-deploy-and-interact-with-contracts" id="compile-deploy-and-interact-with-contracts"></a>

Follow this guide to deploy your contract using Polkadot UI. Once deployed, you will be able to interact with it.
