# Consensus Mechanism

## Introduction

In the blockchain ecosystem, consensus mechanisms are crucial to maintaining the integrity and security of the network. A consensus mechanism is a process used by a network of nodes to agree upon a single data value or a shared state of the network. In other words, it ensures that all nodes in the blockchain have a unified view of the data.

Mandala Chain uses a hybrid consensus mechanism that bridges efficiency and security, critical for maintaining the integrity of the network.&#x20;

Mandala Chain leverages **Aura (Authority Round)** for block production. This mechanism relies on a select group of collators who are responsible for producing new blocks. By using a **Proof-of-Authority (PoA)** setup, the process ensures that only authorized entities generate blocks, streamlining and securing the network operations.

For block finality, Mandala Chain utilizes **GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement)**. This highly efficient protocol ensures that once a block is finalized, it becomes immutable and secure against changes, maintaining the stability of the ledger across the network.

## Block Production

In the Mandala Chain, block production is a critical process managed by **collators**. These key participants are responsible for assembling transactions and proposing new block candidates, ensuring the smooth operation of the blockchain network.

**Key Aspects of Block Production**

1. **Independent Operation**:
   * Block production functions separately from the finality mechanism. This separation allows for efficient and rapid generation of blocks without delays, contributing to the overall performance of the parachain.
2. **Consensus Mechanism**:
   * The Mandala Chain uses the **Aura (Authority Round)** pallet for producing blocks, based on the **Proof-of-Authority (PoA)** model. This model simplifies block production by using a fixed set of trusted collators to author blocks, ensuring security and efficiency.
3. **Deterministic Control**:
   * Aura's design enables a centralized (but trusted) group of collators to create blocks in a scheduled manner. This deterministic approach minimizes conflicts and helps predict network behavior, enhancing reliability.

**Verification of Aura Implementation**

To maintain the integrity and functionality of Aura in Mandala Chain, we follow a systematic verification process:

* **Aura Pallet Verification**: It's essential to ensure that the Aura pallet is present within the chain's runtime. This verification confirms that the pallet is properly integrated and actively managing block production.
* **Aura Keys Check**: The accuracy of Aura keys setup is crucial. We ensure that these keys are correctly configured within the Aura pallet, allowing authorized collators to carry out block production effectively.
* **ASTAR Reference**: We benchmark our process against ASTAR, which also utilizes Aura. Their successful methodology in maintaining Aura's integrity helps validate our approach and provides insights into optimizing our setup.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p><em>When opening our Mandala Node in production, everything is running Aura as expected.</em></p></figcaption></figure>

## Block Finality

Block finality is a crucial aspect of the Mandala Chain, ensuring that once a block is validated, it becomes immutable and secure. This integrity is crucial for maintaining trust across the network.

**How Block Finality Works**

1. **Finality Mechanism**:
   * After collators create block candidates, these blocks are not immediately considered finalized. Instead, validators from the relay chain use the **GRANDPA (GHOST-based Recursive ANcestor Deriving Prefix Agreement)** protocol to finalize them.
2. **Role of GRANDPA**:
   * GRANDPA is a finality protocol used across Polkadot parachains, providing a robust and reliable way to confirm block permanence. It ensures that even if forks occur, only the canonical chain is recognized and extends, eliminating conflicts and duplications.
3. **Nominated Proof-of-Stake (NPoS) System**:
   * Validators are selected via the NPoS system. In this system, nominators stake DOT tokens to endorse validators they trust.
   * Trusted validators are then responsible for executing the GRANDPA protocol, confirming the security and finality of blocks. This consensus process helps maintain the network's overall integrity.
4. **Fork Resolution**:
   * Forks can happen when multiple blocks reference the same parent block. The **fork-choice rule** is applied to decide which chain is legit.
   * In the case of GRANDPA, the longest chain rule is implemented, where the "best" chain is determined by its length. Validators vote to finalize this chain, making it the official record.
5. **Benefits of GRANDPA**:
   * It provides immediate finality once enough votes are collected. This means users can trust that the data on the blockchain won't be altered, enhancing security and trustworthiness.
   * It efficiently resolves forks, ensuring that only one valid chain continues, simplifying the processing and validation tasks across the network.

Through these mechanisms, block finality in the Mandala Chain is robustly managed, ensuring that transactions are secure, irreversible, and reliably recorded in the network’s ledger. This setup not only enhances trust but also optimizes the performance and scalability of the entire system.

## Non-Permissionless Setup

Maintaining a **non-permissionless setup** is essential for ensuring the security and integrity of the Mandala Chain. This framework guarantees that only authorized validators can participate in block production, which is vital for preventing malicious activities and preserving trust in the network.

1. **Validator Selection Control**:
   * The framework includes a **collator selection pallet** that is intentionally configured to prevent **new candidate registrations**. By setting the number of new candidates to zero, we eliminate the possibility of unauthorized entities joining the network as collators. This ensures that only pre-approved, trustworthy participants can produce blocks, enhancing overall network security.
2. **Managing Collator Additions**:
   * New collator additions are carefully controlled through the **invulnerable pallet**. This mechanism allows us to add only those collators deemed "invulnerable," meaning they have passed rigorous trust and reliability assessments. By restricting collator entries to only those with demonstrated resilience and integrity, we mitigate risks associated with introducing potentially harmful actors into the ecosystem.
3. **Verification Process**:
   * To validate the effectiveness of this setup, the Mandala team conducts regular testing by deploying ephemeral Mandala node instances on the **zombienet**. This testing involves attempting to add new collators to observe if the configuration holds firm.
   * If attempts to introduce new collators fail, it confirms that the system is secure and functioning as intended. This proactive verification is crucial in maintaining a strong posture against unauthorized access and reinforces confidence in our operational framework.
4.  **Current Status**:

    * At present, the production environment has successfully configured candidate slots to zero, effectively halting any unauthorized additions. This configuration ensures that the validator set remains secure and reliable, maintaining the integrity of the Mandala Chain.
    * By consistently monitoring and updating this setup, we can adapt to emerging threats while safeguarding the network's foundational principles.

    <figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p><em>How the current state of Mandala Chain's collator pallet looks like.</em></p></figcaption></figure>
