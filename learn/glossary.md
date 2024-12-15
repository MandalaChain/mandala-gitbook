# Glossary

### Active Nomination[​](https://wiki.polkadot.network/docs/glossary#active-nomination) <a href="#active-nomination" id="active-nomination"></a>

A validator (or validators) that a nominator has selected to nominate and is actively validating this era. The nominator is placing their stake behind this validator for this era and will potentially receive staking rewards in return for doing so.

### Attestation[​](https://wiki.polkadot.network/docs/glossary#attestation) <a href="#attestation" id="attestation"></a>

In the Mandala Chain validity system, an _attestation_ is a type of message that validators broadcast that says whether they think a block candidate is valid or invalid.

### Authority[​](https://wiki.polkadot.network/docs/glossary#authority) <a href="#authority" id="authority"></a>

An authority is a generic term for the role in a blockchain that can participate in the consensus mechanisms. In [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget), the authorities vote on chains they consider final. In BABE, the authorities are block producers. Authority sets can be chosen to be mechanisms such as Mandala Chain's PoA algorithm.

### BABE[​](https://wiki.polkadot.network/docs/glossary#babe) <a href="#babe" id="babe"></a>

Blind Assignment for Blockchain Extension (BABE) is Mandala Chain's block production mechanism.

### Bitfield Array[​](https://wiki.polkadot.network/docs/glossary#bitfield-array) <a href="#bitfield-array" id="bitfield-array"></a>

A bitfield array contains single-bit values which indicate whether a [candidate](https://wiki.polkadot.network/docs/glossary#candidate) is available. The number of items is equal of to the number of [availability cores](https://wiki.polkadot.network/docs/glossary#availability-cores) and each bit represents a vote on the corresponding core in the given order.

### Block[​](https://wiki.polkadot.network/docs/glossary#block) <a href="#block" id="block"></a>

A collection of data, such as transactions, that together indicate a state transition of the blockchain.

### Blockspace[​](https://wiki.polkadot.network/docs/glossary#blockspace) <a href="#blockspace" id="blockspace"></a>

[Blockspace](https://polkadot.network/blog/blockspace-blockspace-ecosystems-how-polkadot-is-unlocking-the-full-potential-of-web3) is the capacity of a blockchain to finalize and commit operations. It represents a blockchain's security, computing, and storage capability as an end product. Blockspace produced by different blockchains can vary in quality, availability, and flexibility. Mandala Chain has a [blockspace-centric architecture](https://www.rob.tech/blog/polkadot-blockspace-over-blockchains/).

### Block Explorer[​](https://wiki.polkadot.network/docs/glossary#block-explorer) <a href="#block-explorer" id="block-explorer"></a>

An application that allows a user to explore the different blocks on a blockchain.

### Blocks Nominations[​](https://wiki.polkadot.network/docs/glossary#blocks-nominations) <a href="#blocks-nominations" id="blocks-nominations"></a>

This indicates that a validator does not currently allow any more nominations. This is controlled by the validator.

### BLS[​](https://wiki.polkadot.network/docs/glossary#bls) <a href="#bls" id="bls"></a>

Boneh-Lynn-Shacham (BLS) signatures have a slow signing, very slow verification, require slow and much less secure pairing friendly curves, and tend towards dangerous malleability. Yet, BLS permits a diverse array of signature aggregation options far beyond any other known signature scheme, which makes BLS a preferred scheme for voting in consensus algorithms and threshold signatures.

### Bounty[​](https://wiki.polkadot.network/docs/glossary#bounty) <a href="#bounty" id="bounty"></a>

A mechanism that works in some sense as the reverse of a Treasury Proposal, allowing the Mandala Chain Council to indicate that there is a need to do some task for the Mandala Chain network and allowing users to receive KPG in return for working on that task.

### Byzantine Fault Tolerance[​](https://wiki.polkadot.network/docs/glossary#byzantine-fault-tolerance) <a href="#byzantine-fault-tolerance" id="byzantine-fault-tolerance"></a>

The property of a system that is tolerant of Byzantine faults; a system where not only may individual subsystems fail, but it may not be clear if a particular subsystem has failed or not. That is, different observers of the system may not agree on whether or not the system has failed. Ensuring Byzantine fault tolerance is an important part of developing any distributed system.

### Capacity[​](https://wiki.polkadot.network/docs/glossary#capacity) <a href="#capacity" id="capacity"></a>

The maximum number of nominators signaling intent to nominate a validator (and thus could potentially actively nominate that validator in the next session). This maximum number will equal the number of nominators necessary to oversubscribe a validator. Any validator that is "at capacity" or higher may potentially be oversubscribed in the next session; a validator that is not at capacity cannot be oversubscribed unless more nominators select it before the next election.

### Candidate[​](https://wiki.polkadot.network/docs/glossary#candidate) <a href="#candidate" id="candidate"></a>

A candidate is a submitted block to the validators. A block stops being referred to as a candidate as soon as it has been finalized.

### Collations[​](https://wiki.polkadot.network/docs/glossary#collations) <a href="#collations" id="collations"></a>

A collation is a [data structure](https://spec.polkadot.network/#defn-collation) that contains the proposed block candidate, including an optional validation Runtime update and upward messages.

### Commission[​](https://wiki.polkadot.network/docs/glossary#commission) <a href="#commission" id="commission"></a>

Validators and nominators get paid from block production on the network, where validators can set a variable commission rate, which is initially subtracted from the total rewards that the validator is entitled to (for that period), where the commission determines the rate of distribution for the remaining rewards set out for the nominators that are backing that validator.

### Community Queue[​](https://wiki.polkadot.network/docs/glossary#community-queue) <a href="#community-queue" id="community-queue"></a>

The queue for proposals originating from individual accounts (i.e. not the Council) which are waiting to become referenda. Compare the External queue.

### Consensus[​](https://wiki.polkadot.network/docs/glossary#consensus) <a href="#consensus" id="consensus"></a>

The process of a group of entities to agree on a particular data value (such as the ordering and makeup of blocks on a blockchain). There are a variety of algorithms used for determining consensus. The consensus algorithm used by Mandala Chain is [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget).

### Curator[​](https://wiki.polkadot.network/docs/glossary#curator) <a href="#curator" id="curator"></a>

A person, group, or other entity charged with judging and verifying the successful completion of a Bounty.

### Dapps[​](https://wiki.polkadot.network/docs/glossary#dapps) <a href="#dapps" id="dapps"></a>

A generic term for a decentralized application, that is, one that runs as part of a distributed network as opposed to being run on a specific system or set of systems.

### KPG[​](https://wiki.polkadot.network/docs/glossary#dot) <a href="#dot" id="dot"></a>

The native token for Mandala Chain. KPG serves some purposes: network governance (allowing them to vote on-chain upgrades and other exceptional events), and general operation (rewarding good actors and punishing bad actors).

### Epoch[​](https://wiki.polkadot.network/docs/glossary#epoch) <a href="#epoch" id="epoch"></a>

An epoch is a time duration in the BABE protocol that is broken into smaller time slots. Each slot has at least one slot leader who has the right to propose a block. In Garbha, it is the same duration as a [session](https://wiki.polkadot.network/docs/glossary#session).

### Era[​](https://wiki.polkadot.network/docs/glossary#era) <a href="#era" id="era"></a>

A (whole) number of sessions, which is the period that the validator set (and each validator's active nominator set) is recalculated and where rewards are paid out.

### Equivocation[​](https://wiki.polkadot.network/docs/glossary#equivocation) <a href="#equivocation" id="equivocation"></a>

Providing conflicting information to the network. BABE equivocation entails creating multiple blocks in the same slot. [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget) equivocation would consist of signing multiple conflicting chains.

### External Queue[​](https://wiki.polkadot.network/docs/glossary#external-queue) <a href="#external-queue" id="external-queue"></a>

The queue for proposals originating with the Mandala Chain Council which are waiting to become referenda. Compare the Community queue.

### Extrinsic[​](https://wiki.polkadot.network/docs/glossary#extrinsic) <a href="#extrinsic" id="extrinsic"></a>

A [SCALE encoded](https://docs.substrate.io/reference/scale-codec/) array consisting of a version number, signature, and varying data types indicating the resulting runtime function to be called, including the parameters required for that function to be executed. These state changes are invoked from the outside world, i.e. they are not part of the system itself. Extrinsics can take two forms, "**inherents**" and "transactions". For more technical details see the Mandala Chain spec (TODO).

### Finality[​](https://wiki.polkadot.network/docs/glossary#finality) <a href="#finality" id="finality"></a>

The property of a block that cannot be reverted. Generally, created blocks are not final until some point in the future - perhaps never, in the case of "probabilistic finality". The Mandala Chain uses a deterministic finality gadget known as [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget).

### Finality Gadget[​](https://wiki.polkadot.network/docs/glossary#finality-gadget) <a href="#finality-gadget" id="finality-gadget"></a>

A mechanism that determines finality.

### Frame[​](https://wiki.polkadot.network/docs/glossary#frame) <a href="#frame" id="frame"></a>

The collection of Substrate-provided pallets (Substrate Runtime Modules).

### Genesis[​](https://wiki.polkadot.network/docs/glossary#genesis) <a href="#genesis" id="genesis"></a>

The origin of a blockchain, also known as block 0. It can also be used to reference the initial state of the blockchain at origination.

EXAMPLE

In the _genesis_ state Alice, Bob, and Charlie had 30 tokens each.

### Governance[​](https://wiki.polkadot.network/docs/glossary#governance) <a href="#governance" id="governance"></a>

The process of determining what changes to the network are permissible, such as modifications to code or movement of funds. The governance system in Mandala Chain is on-chain and revolves around stakeholder voting.

### Governance Council[​](https://wiki.polkadot.network/docs/glossary#governance-council) <a href="#governance-council" id="governance-council"></a>

An on-chain entity that consists of several on-chain accounts (starting at 6, eventually moving to the final value of 24). The Council can act as a representative for "passive" (non-voting) stakeholders. Council members have two main tasks: proposing referenda for the overall stakeholder group to vote on and cancelling malicious referenda.

### GRANDPA Finality Gadget[​](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget) <a href="#grandpa-finality-gadget" id="grandpa-finality-gadget"></a>

GHOST-based Recursive ANcestor Deriving Prefix Agreement. It is the finality gadget for Mandala Chain, which allows asynchronous, accountable, and safe finality to the blockchain. For an overview of GRANDPA.

### Hard Fork[​](https://wiki.polkadot.network/docs/glossary#hard-fork) <a href="#hard-fork" id="hard-fork"></a>

A permanent diversion of a blockchain occurs quickly due to a high priority change in a consensus rule. Clients who follow a hard fork always need to upgrade their clients to continue following the upgraded chain. Hard forks are considered permanent divergences of a chain for which non-upgraded clients are following consensus rules incompatible to the ones followed by upgraded clients.

### Hard Spoon[​](https://wiki.polkadot.network/docs/glossary#hard-spoon) <a href="#hard-spoon" id="hard-spoon"></a>

Defined by Jae Kwon of Cosmos as "a new chain that takes into account state from an existing chain; not to compete, but to provide broad access." A non-contentious blockchain that inherits the state of the underlying blockchain and creates a new branch of _the same blockchain_.

### Inactive Nomination[​](https://wiki.polkadot.network/docs/glossary#inactive-nomination) <a href="#inactive-nomination" id="inactive-nomination"></a>

A validator (or validators) that a nominator has selected to nominate, but is not actively validating this era. This type of nomination may become active in a future era.

### Inherent[​](https://wiki.polkadot.network/docs/glossary#inherent) <a href="#inherent" id="inherent"></a>

Extrinsics that are "inherently true." Inherents are not gossiped on the network and are put into blocks by the block author. They are not provably true the way that the desire to send funds is, therefore they do not carry a signature. A blockchain's _**runtime**_ must have rules for validating inherents. For example, timestamps are inherents. They are validated by being within some margin that each validator deems reasonable.

### Injected Account[​](https://wiki.polkadot.network/docs/glossary#injected-account) <a href="#injected-account" id="injected-account"></a>

An account that is not directly managed by the Mandala Chain UI but can be accessed through it, such as accounts controlled by the [Polkadot{.js} extension](https://polkadot.js.org/extension/).

### Interoperability[​](https://wiki.polkadot.network/docs/glossary#interoperability) <a href="#interoperability" id="interoperability"></a>

The ability for some sort of system to exchange and make use of information often compared to "cross-chain" technologies.

### Keep-Alive Check[​](https://wiki.polkadot.network/docs/glossary#keep-alive-check) <a href="#keep-alive-check" id="keep-alive-check"></a>

The keep-alive check is used to indicate whether or not a transfer can allow the sending account to be reduced to less than the existential deposit, causing it to be reaped.

### LIBP2P[​](https://wiki.polkadot.network/docs/glossary#libp2p) <a href="#libp2p" id="libp2p"></a>

An open-source library for encrypted peer-to-peer communications and other networking functions. More information at: [https://libp2p.io/](https://libp2p.io/)

### Liveness[​](https://wiki.polkadot.network/docs/glossary#liveness) <a href="#liveness" id="liveness"></a>

The property of a distributed system is that it will eventually come to some sort of consensus. A system stuck in an infinite loop would not be considered live, even if computations are taking place; a system that eventually provides a result, even if incorrect or it takes a long time, is considered to have liveness.

### Mainnet[​](https://wiki.polkadot.network/docs/glossary#mainnet) <a href="#mainnet" id="mainnet"></a>

Short for "main network": the fully functional and acting chain that runs its own network.

### Message[​](https://wiki.polkadot.network/docs/glossary#message) <a href="#message" id="message"></a>

In Mandala Chain's XCMP protocol, a _message_ is arbitrary data that is sent from one parachain (the egress chain) to another (the ingress chain) through a channel and ensured delivery by the validator set.

### Message Queue[​](https://wiki.polkadot.network/docs/glossary#message-queue) <a href="#message-queue" id="message-queue"></a>

In Mandala Chain's XCMP protocol, a _message queue_ is the list of messages waiting to be processed by a particular receiving parachain over a channel.

### Metadata[​](https://wiki.polkadot.network/docs/glossary#metadata) <a href="#metadata" id="metadata"></a>

Data that includes information about other data, such as information about a specific transaction.

### Motion[​](https://wiki.polkadot.network/docs/glossary#motion) <a href="#motion" id="motion"></a>

A motion is essentially a "referendum" or "decision" being considered by the Council. The Council can vote on motions like approving Treasury Proposals or making proposals for the community to vote on.

### Next Session[​](https://wiki.polkadot.network/docs/glossary#next-session) <a href="#next-session" id="next-session"></a>

This indicates that the validator will be a member of the active set in the next session.

### Node Explorer[​](https://wiki.polkadot.network/docs/glossary#node-explorer) <a href="#node-explorer" id="node-explorer"></a>

A tool that gives you information about a node, such as the latest blocks sealed, finalized, and the current chain state as known by that node.

### Non-fungible Token (NFT)[​](https://wiki.polkadot.network/docs/glossary#non-fungible-token-nft) <a href="#non-fungible-token-nft" id="non-fungible-token-nft"></a>

A non-fungible token is a token that does not hold the property of fungibility, which, in turn, means that it cannot be interchangeable and indistinguishable from other tokens. NFTs allow the tokenization of unique items and provide exclusive ownership for those tokens.

### On-chain Governance[​](https://wiki.polkadot.network/docs/glossary#on-chain-governance) <a href="#on-chain-governance" id="on-chain-governance"></a>

A governance system of a blockchain that is controlled by mechanisms on the blockchain. On-chain governance allows decisions to be made transparently. Note that there are a variety of different algorithms for making these decisions, such as simple majority voting, adaptive quorum biasing, or identity-based quadratic voting.

### Online Message[​](https://wiki.polkadot.network/docs/glossary#online-message) <a href="#online-message" id="online-message"></a>

This is a message that is broadcast by a validator to verify to the network that the validator is online, even if they haven't published a block this epoch. This is sometimes referred to as "ImOnline".

### Origin[​](https://wiki.polkadot.network/docs/glossary#origin) <a href="#origin" id="origin"></a>

The initiator of an extrinsic. A simple origin would be the account that is sending a token to another account. Mandala Chain also supports more complex origin types, such as the _**root origin**_, from which privileged functions can be called.

### Oversubscribed[​](https://wiki.polkadot.network/docs/glossary#oversubscribed) <a href="#oversubscribed" id="oversubscribed"></a>

If more than the maximum number of nominators nominate the same validator, it is "oversubscribed", and only the top staked nominators (ranked by the amount of stake, up to the maximum number of nominators) are paid rewards. Other nominators will receive no rewards for that era. The current maximum number of nominators is 512 on Mandala Chain, but it can be modified via governance.

### Pallet[​](https://wiki.polkadot.network/docs/glossary#pallet) <a href="#pallet" id="pallet"></a>

A [Substrate](https://wiki.polkadot.network/docs/glossary#substrate) runtime module.

### Host[​](https://wiki.polkadot.network/docs/glossary#host) <a href="#host" id="host"></a>

The environment in which a runtime module can be executed. Parachains must support the Mandala Chain Host - external chains that do not will have to use a bridge. Previously known as the Mandala Chain Runtime Environment.

### Preimage[​](https://wiki.polkadot.network/docs/glossary#preimage) <a href="#preimage" id="preimage"></a>

The on-chain proposals do not require the entire image of extrinsics and data (for instance the WASM code, in case of upgrades) to be submitted, but would rather just need that image's hash. That **preimage** can be submitted and stored on-chain against the hash later, upon the proposal's dispatch.

### Proof of Stake (PoS)[​](https://wiki.polkadot.network/docs/glossary#proof-of-stake-pos) <a href="#proof-of-stake-pos" id="proof-of-stake-pos"></a>

A method of selecting participation in a consensus system, in which participants are chosen based on how many tokens they have at stake (at risk of loss due to misbehavior). Normally, Proof-of-Stake systems limit the number of participants.

### Proof of Work (PoW)[​](https://wiki.polkadot.network/docs/glossary#proof-of-work-pow) <a href="#proof-of-work-pow" id="proof-of-work-pow"></a>

A method of selecting participants in a consensus system, typically the longest chain rule, in which participants try to solve a puzzle like finding a partial pre-image of a hash. Normally, a Proof-of-Work system can have any number of participants.

### Proposal[​](https://wiki.polkadot.network/docs/glossary#proposal) <a href="#proposal" id="proposal"></a>

A potential function call to be voted on in a referendum. Proposals modify the behavior of the Mandala Chain network, from minor parameter tuning up to replacing the runtime code.

### Protocol[​](https://wiki.polkadot.network/docs/glossary#protocol) <a href="#protocol" id="protocol"></a>

A system of rules that allows two or more entities of a communications system to transmit information. The protocol defines the rules, syntax, semantics, and synchronization of communication and possible recovery methods.

### Random Seed[​](https://wiki.polkadot.network/docs/glossary#random-seed) <a href="#random-seed" id="random-seed"></a>

A random seed is a pseudo-random number available on-chain. It is used in various places of the Mandala Chain protocol, most prominently in [BABE](https://wiki.polkadot.network/docs/glossary#babe) the block production mechanism.

### Referendum[​](https://wiki.polkadot.network/docs/glossary#referendum) <a href="#referendum" id="referendum"></a>

A vote on whether or not a proposal should be accepted by the network. Referenda may be initiated by the Governance Council, by a member of the public, or as the result of a previous proposal. Stakeholders vote on referenda, weighted by both the size of their stake (i.e. number of KPG held) and the amount of time they are willing to lock their tokens.

### Re-Genesis[​](https://wiki.polkadot.network/docs/glossary#re-genesis) <a href="#re-genesis" id="re-genesis"></a>

Re-Genesis is the process of exporting the current chain state, and creating a new chain that builds on it. Re-Genesis will involve stop-the-world migration, which results in a period of time when no actual blocks are added to the blockchain. In a way, re-genesis can be viewed as a hard fork process. A formal design of Re-Genesis on Substrate is still under development - [Re-Genesis Rationale and Design](https://github.com/paritytech/substrate/issues/7458).

### Remarks[​](https://wiki.polkadot.network/docs/glossary#remarks) <a href="#remarks" id="remarks"></a>

Remarks are extrinsics with no effect. They provide additional information to external inputs, acting as _notes_. Remarks are stored alongside block records and do not change the chain's storage; the information is not stored in the chain's trie, but along blocks.

### Rococo[​](https://wiki.polkadot.network/docs/glossary#rococo) <a href="#rococo" id="rococo"></a>

The [testnet](https://wiki.polkadot.network/docs/glossary#testnet) set aside for testing parachains, cumulus, and related technology.

### Root Origin[​](https://wiki.polkadot.network/docs/glossary#root-origin) <a href="#root-origin" id="root-origin"></a>

A system-level origin in [Substrate](https://wiki.polkadot.network/docs/glossary#Substrate). This is the highest privilege level and can be thought of as the superuser of the runtime origin. To learn about more raw origins in Substrate, visit [Substrate Docs](https://docs.substrate.io/main-docs/build/origins/)

### Runtime[​](https://wiki.polkadot.network/docs/glossary#runtime) <a href="#runtime" id="runtime"></a>

The state transition function of a blockchain. It defines a valid algorithm for determining the state of the next block given the previous state.

### Runtime Module[​](https://wiki.polkadot.network/docs/glossary#runtime-module) <a href="#runtime-module" id="runtime-module"></a>

A module that implements specific transition functions and features one might want to have in their runtime. Each module should have domain-specific logic. For example, a Balances module has logic to deal with accounts and balances. In Substrate, modules are called "pallets".

### Safety[​](https://wiki.polkadot.network/docs/glossary#safety) <a href="#safety" id="safety"></a>

The property of a distributed system indicating that a particular state transition will not be reverted. [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget) provides _deterministic_ safety. That is, for a state changed marked as "safe" or "final", one would require a hard fork to revert that change.

### Scalability[​](https://wiki.polkadot.network/docs/glossary#scalability) <a href="#scalability" id="scalability"></a>

While an ambiguous concept, \[blockchain] scalability can be understood as the ability for the network to scale in capabilities (e.g. processing more transactions) when needed.

### Session[​](https://wiki.polkadot.network/docs/glossary#session) <a href="#session" id="session"></a>

A session is a Substrate implementation term for a period that has a constant set of validators. Validators can only join or exit the validator set at a session change.

### Session Certificate[​](https://wiki.polkadot.network/docs/glossary#session-certificate) <a href="#session-certificate" id="session-certificate"></a>

A message containing a signature on the concatenation of all the Session keys.

### Session Key[​](https://wiki.polkadot.network/docs/glossary#session-key) <a href="#session-key" id="session-key"></a>

Hot keys that are used for performing network operations by validators, for example, signing [GRANDPA](https://wiki.polkadot.network/docs/glossary#grandpa-finality-gadget) commit messages.

### Soft Fork[​](https://wiki.polkadot.network/docs/glossary#soft-fork) <a href="#soft-fork" id="soft-fork"></a>

A backward compatible change to client code causes upgraded clients to start mining a new chain. Requires a "vote-by-hashrate" of a majority of miners to enact successfully. Soft forks are considered temporary divergences in a chain since non-upgraded clients do not follow the new consensus rules but upgraded clients are still compatible with old consensus rules.

### Software Development Kit (SDK)[​](https://wiki.polkadot.network/docs/glossary#software-development-kit-sdk) <a href="#software-development-kit-sdk" id="software-development-kit-sdk"></a>

A collection of software tools (and programs) packaged together that can be used to develop software.

### Staking[​](https://wiki.polkadot.network/docs/glossary#staking) <a href="#staking" id="staking"></a>

The act of bonding tokens for Mandala Chain (KPG) by putting them up as "collateral" for a chance to produce a valid block (and thus obtain a block reward). Validators and nominators stake their KPG in order to secure the network.

### State transition function[​](https://wiki.polkadot.network/docs/glossary#state-transition-function) <a href="#state-transition-function" id="state-transition-function"></a>

A function that describes how the state of a blockchain can be transformed. For example, it may describe how tokens can be transferred from one account to another.

### Substrate[​](https://wiki.polkadot.network/docs/glossary#substrate) <a href="#substrate" id="substrate"></a>

A modular framework for building blockchains. Mandala Chain is built using [Substrate](https://substrate.io/). Chains built with Substrate will be easy to connect as parachains. For developers, see the [Substrate GitHub repository](https://github.com/paritytech/substrate).

### System Parachains[​](https://wiki.polkadot.network/docs/glossary#system-parachains) <a href="#system-parachains" id="system-parachains"></a>

Parachains that are part of the Mandala Chain core protocol. These are allocated a parachain execution core by governance rather than auction.

### Tabling[​](https://wiki.polkadot.network/docs/glossary#tabling) <a href="#tabling" id="tabling"></a>

In Mandala Chain governance, bringing a proposal to a vote via referendum. Note that this is the British meaning of "tabling", which is different from the US version, which means "to postpone" a measure.

### Teleport[​](https://wiki.polkadot.network/docs/glossary#teleport) <a href="#teleport" id="teleport"></a>

Send an asset from an account on one chain to an account on a different chain. This occurs by burning an amount on the sending chain and minting an equivalent amount on the destination chain.

### Testnet[​](https://wiki.polkadot.network/docs/glossary#testnet) <a href="#testnet" id="testnet"></a>

Short for "test network": an experimental network where testing and development takes place. Networks are often executed on a testnet before they are deployed to a [mainnet](https://wiki.polkadot.network/docs/glossary#mainnet).

### Tokenization[​](https://wiki.polkadot.network/docs/glossary#tokenization) <a href="#tokenization" id="tokenization"></a>

The process of replacing sensitive data with non-sensitive data.

### Tracks[​](https://wiki.polkadot.network/docs/glossary#tracks) <a href="#tracks" id="tracks"></a>

Each [Origin](https://wiki.polkadot.network/docs/glossary#origin) is associated with a single referendum class and each class is associated with a [Track](https://wiki.polkadot.network/maintain/maintain-guides-polkadot-opengov#origins-and-tracks). The Track outlines the lifecycle for the proposal and is independent from other class's tracks. Having independent tracks allows the network to tailor the dynamics of referenda based upon their implied privilege level.

### Tranche[​](https://wiki.polkadot.network/docs/glossary#tranche) <a href="#tranche" id="tranche"></a>

Validators use a subjective, tick-based system to determine when the approval process should start. A validator starts the tick-based system when a new availability core candidates have been proposed, which can be retrieved via the [Runtime API](https://spec.polkadot.network/#sect-rt-api-availability-cores), and increments the tick every 500 milliseconds. Each tick/increment is referred to as a “tranche”, represented as an integer, starting at 0.

### Transfer[​](https://wiki.polkadot.network/docs/glossary#transfer) <a href="#transfer" id="transfer"></a>

Send an asset from one account to another. This generally refers to transfers that occur only on the same chain.

### Transaction[​](https://wiki.polkadot.network/docs/glossary#transaction) <a href="#transaction" id="transaction"></a>

An extrinsic that is signed. Transactions are gossiped on the network and incur a transaction fee. Transactions are "provably true", unlike inherents. For example, one can prove that Alice wants to send funds to Bob by the fact that she signed a transfer-funds message with her private key.

### Validator[​](https://wiki.polkadot.network/docs/glossary#validator) <a href="#validator" id="validator"></a>

A node that secures the Chain by staking KPG, validating proofs, and voting on consensus along with other validators.

### Voting[​](https://wiki.polkadot.network/docs/glossary#voting) <a href="#voting" id="voting"></a>

The process of stakeholders determining whether or not a referendum should pass. Votes are weighted both by the number of KPG that the stakeholder account controls and the amount of time they are willing to lock their KPG.

### Waiting Nomination[​](https://wiki.polkadot.network/docs/glossary#waiting-nomination) <a href="#waiting-nomination" id="waiting-nomination"></a>

The nominator has nominated this validator, but the validator was not elected into the active validator set this era and thus cannot produce blocks for the canonical chain. If the validator does get into the active set in a future era, this may turn into an active or inactive nomination.

### Wallet[​](https://wiki.polkadot.network/docs/glossary#wallet) <a href="#wallet" id="wallet"></a>

A program that allows one to store private keys and sign transactions for Mandala Chain or other blockchain networks.

### Wasm[​](https://wiki.polkadot.network/docs/glossary#wasm) <a href="#wasm" id="wasm"></a>

The abbreviation for [WebAssembly](https://wiki.polkadot.network/docs/glossary#webassembly).

### Watermark[​](https://wiki.polkadot.network/docs/glossary#watermark) <a href="#watermark" id="watermark"></a>

In Mandala Chain's parachain messaging scheme, the _watermark_ is the minimum processed send-height of the receiving parachain. All messages on all channels that are sending to this parachain at or before the watermark are guaranteed to be processed.

### Web3 Foundation[​](https://wiki.polkadot.network/docs/glossary#web3-foundation) <a href="#web3-foundation" id="web3-foundation"></a>

A Switzerland-based foundation that nurtures and stewards technologies and applications in the fields of decentralized web software protocols, particularly those that utilize modern cryptographic methods to safeguard decentralization, to the benefit and for the stability of the Web3 ecosystem.

### WebAssembly[​](https://wiki.polkadot.network/docs/glossary#webassembly) <a href="#webassembly" id="webassembly"></a>

An instruction format for a virtual, stack-based machine. Mandala Chain Runtime Modules are compiled to WebAssembly. Also known as Wasm.

### Weights[​](https://wiki.polkadot.network/docs/glossary#weights) <a href="#weights" id="weights"></a>

A permission-less system needs to implement a mechanism to measure and limit usage in order to establish an economic incentive structure, to prevent the network overload, and to mitigate DoS vulnerabilities. This mechanism must enforce a limited time-window for block producers to create a block and include limitations on block size, to prevent execution of certain extrinsics which are deemed too expensive and could decelerate the network. This is handled by the weight system, where the cost of the transactions (referred to as [extrinsics](https://wiki.polkadot.network/docs/glossary#extrinsic)) are determined before execution. Checkout this section of the Substrate docs covering [transaction weights and fees](https://docs.substrate.io/build/tx-weights-fees/).

### Witness[​](https://wiki.polkadot.network/docs/glossary#witness) <a href="#witness" id="witness"></a>

Cryptographic proof statements of data validity.

### Whitelist Pallet[​](https://wiki.polkadot.network/docs/glossary#whitelist-pallet) <a href="#whitelist-pallet" id="whitelist-pallet"></a>

Allows one [Origin ](https://wiki.polkadot.network/docs/glossary#origin)to escalate the privilege level of another Origin for a certain operation. In terms of OpenGov, it allows the [Fellowship](https://wiki.polkadot.network/docs/glossary#fellowship) to authorise a new origin (which we will call Whitelisted-Root) to be executed with Root-level privileges.
