# Block Authorization and Finality

## Block Authors

There are validators on the Mandala Chain who participate in the consensus mechanism to produce the blocks based on validity statements from other validators. These validators are called _block authors;_ they are selected by AURA consensus and can note up to one backable candidate for each block to include in the blockchain. A backable candidate included in the chain is considered backed in that fork of the chain.

In a Mandala Chain block, block authors will only include candidate receipts that have a parent candidate receipt in an earlier block. This ensures the Mandala Chain blocks follow a valid chain. Also, the block authors will only include a receipt for which they have an erasure coding chunk, ensuring that the system can perform the next round of availability and validity checks.
