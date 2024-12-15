---
hidden: true
---

# Run a Validator Node

## Overview

### Preliminaries

Running a validator on a live network is a lot of responsibility! You will be accountable for not only your own stake but also the stake of your current nominators. If you make a mistake and get slashed, your tokens and your reputation will be at risk. However, running a validator can also be very rewarding, knowing that you contribute to the security of a decentralized network while accumulating rewards.

> DANGER
>
> It is highly recommended that you have significant system administration experience before attempting to run your own validator.
>
> You must be able to handle technical issues and anomalies with your node, which you must be able to tackle yourself. Being a validator involves more than just executing the Mandala Chain binary.

Since security is essential to running a successful validator, you should take a look at the [secure validator](https://wiki.polkadot.network/docs/maintain-guides-secure-validator) information to make sure you understand the factors to consider when constructing your infrastructure. As you progress as a validator, you will likely want to use this repository as a _starting point_ for any modifications and customizations.

If you need help, please contact the _**Mandala Technical Support**_ on Telegram. The team and other validators are there to help answer questions and provide tips from experience.

### Role of validators in the Mandala Chain ecosystem[​](https://docs.astar.network/docs/build/nodes/collator/learn#role-of-collators-in-the-astar-ecosystem) <a href="#role-of-collators-in-the-astar-ecosystem" id="role-of-collators-in-the-astar-ecosystem"></a>

Validators maintain our ecosystem by collecting user transactions and producing state transition proofs. In other words, validators maintain the network by aggregating blockchain transactions into block candidates and producing state transition proofs based on those blocks.

The validators also secure the network. If a candidate block is invalid, it will get rejected. On the contrary, too many validators may slow down the network. The only nefarious power validators have transaction censorship. The blockchain must only ensure some neutral validators to prevent censorship - but not necessarily a majority. Theoretically, the censorship problem is solved by having just one honest validator.

The performance of the network depends directly on validators. To ensure optimal network performance, it runs on _Proof-of-Authority_ (PoA). This means every validator has to be registered beforehand.

***

### Aura PoA Consensus[​](https://docs.astar.network/docs/build/nodes/collator/learn#aura-pos-consensus) <a href="#aura-pos-consensus" id="aura-pos-consensus"></a>

The first phase of PoA implementation was via the Aura pallet. Aura PoA Phase - permissioned block authoring and collator session key setup for the Mandala Chain ecosystem.&#x20;

**Let’s break down the latest phase:**

* **Validator staking**: validators can now start with securing the network. This will be with a minimum bond of a fixed amount of tokens.
* **Network inflation**: The Mandala Chain Niskala testnet has a 10% inflation. This 10% is based on a perfect block production every 6 seconds.
* **Rewards**: A fixed amount will be created at each block and divided between the treasury and validators.

A validator is rewarded a fixed amount for each block produced.

***

### Validator election mechanism[​](https://docs.astar.network/docs/build/nodes/collator/learn#collator-election-mechanism) <a href="#collator-election-mechanism" id="collator-election-mechanism"></a>

#### Election process[​](https://docs.astar.network/docs/build/nodes/collator/learn#election-process) <a href="#election-process" id="election-process"></a>

To join the election process, you must register for a validator and bond tokens. Please take a look at the Validator Requirements for details. When your node fits the parameters and checks all the boxes to become a validator, it will be added to the chain. **Note: If your validator doesn’t produce blocks during two sessions (2h), it will be kicked out.**

***

### Validator reward distribution mechanism[​](https://docs.astar.network/docs/build/nodes/collator/learn#collator-reward-distribution-mechanism) <a href="#collator-reward-distribution-mechanism" id="collator-reward-distribution-mechanism"></a>

At every block you produce as a validator, rewards will automatically be transferred to your account. The reward includes block reward + fees.

***

### Slashing mechanism[​](https://docs.astar.network/docs/build/nodes/collator/learn#slash-mechanism) <a href="#slash-mechanism" id="slash-mechanism"></a>

A slashing mechanism will be implemented on The Mandala Chain networks - a validator that doesn't produce blocks during two sessions (2 hours) will be slashed 1% of its total stake and kicked out of the active collator set. This slashing ensures the best block rate and prevents malicious actors from harming the network without financial consequences.

***

### How many KPGs do I need to become an active Validator?

You can have a rough estimate of that by using the methods listed [here](validator-requirement.md). To be elected into the set, you need a minimum stake behind your validator. This means that, at minimum, you will need enough KPG to set up stash and staking proxy [accounts](https://wiki.polkadot.network/docs/learn-cryptography) with the existential deposit, plus a little extra for transaction fees. The rest can come from nominators. To understand how validators are elected, refer to the _**PoA Election**_ page.
