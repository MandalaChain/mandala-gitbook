# Validator Rules

Validators secure the chain by staking KPG, validating proofs of block production, and participating in consensus with other validators.

Validators play a crucial role in adding new blocks to the blockchain. They guarantee that each validator follows its unique rules and can pass messages between shards in a trust-free environment.

Validators maintain the network by collecting user transactions and producing state transition proofs. Validators also maintain a full node for the Mandala Chain, meaning they retain all necessary information to author new blocks and execute transactions like miners do on PoW blockchains. Under normal circumstances, they will collate and execute transactions to create an unsealed block and provide it to one or more validators responsible for proposing a block.

Validators also provide security guarantees. If a block is invalid, it will get rejected by validators. The validators are required to check the validity of submitted candidates, followed by issuing and collecting statements about the validity of candidates to other validators. This process is known as _candidate backing_. Validators receive an arbitrary number of block candidates with associated PoV from untrusted validators. A candidate is considered backable when at least 2/3 of all assigned validators have issued a valid statement about that candidate.

The validator must successfully verify the  conditions in the following order:

1. The candidate does not exceed any parameters in the persisted validation data.
2. The signature of the validator is valid.
3. Validate the candidate by executing the Runtime.

Once a candidate meets specified criteria for inclusion, the selected block author chooses any backable block candidates and includes those into the blockchain. We say the candidate blocks are backed.

The assumption that having more validators is better or more secure is incorrect. On the contrary, too many validators may slow down the network. The only nefarious power validators have transaction censorship. To prevent censorship, the blockchain only needs to ensure that there are some neutral validators - but not necessarily a majority. Theoretically, the censorship problem is solved by having just one honest validator.
