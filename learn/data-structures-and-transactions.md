# Data Structures and Transactions

## Data Structures

### Collations

Collations are proposed candidates for the Mandala Chain validators. The Mandala Chain network protocol is agnostic on what candidate production mechanism each parachain uses and does not specify or mandate specific production methods (e.g., BABE-GRANDPA, Aura, etc.). Furthermore, the validator host implementation does not directly interpret or process the candidate's internal transactions but relies on the layer 1 Runtime to validate the candidate.&#x20;

> A collation is a data structure that contains the proposed block candidate, including an optional validation Runtime update and upward messages. The collation data structure, C, is a data structure of the following format:

$$
C=(M,H,R,h,P,p,w)
$$

$$
M=(u 
n
​
 ,…u 
m
​
 )
$$

$$
H=(z 
n
​
 ,…z 
m
​
 )
$$

> where:
>
> * $$M$$ is an array of upward messages, _u_, interpreted by the chain itself.
> * _H_ is an array of outbound horizontal messages, _z_.
> * _R_ is an Option type which can contain a Runtime update. The new Runtime code is an array of bytes.
> * ℎ is the head data produced as a result of execution of the blockchain specific logic.
> * _P_ is the PoV block.
> * _p_ is an unsigned 32-bit integer indicating the number of processed downward messages.
> * _w_ is an unsigned 32-bit integer indicating the mark up to which all inbound HRMP messages have been processed by the blockchain.

## Transaction Construction and Signing

> This page will discuss the transaction format in Mandala Chain and how to create, sign, and broadcast transactions. Like the other pages in this guide, this page demonstrates some of the available tools. Always refer to each tool's documentation when integrating.

### Transaction Format

Mandala Chain has some basic transaction information that is common to all transactions.

* _Address_: The SS58-encoded address of the sending account.
* _Block Hash_: The hash of the checkpoint block.
* Block Number: The number of the checkpoint block.
* _Genesis Hash_: The genesis hash of the chain
* _Metadata_: The SCALE-encoded metadata for the runtime when submitted.
* _Nonce_: The nonce for this transaction.\*&#x20;
* _Spec Version_: The current spec version for the runtime.&#x20;
* _Transaction Version_: The current version of the transaction format.&#x20;
* _Tip_: Optional, the tip to increase transaction priority.&#x20;
* _Era Period:_ Optional, the number of blocks after the checkpoint for which a transaction is valid. If zero, the transaction is immortal.

{% hint style="warning" %}
There are risks to making a transaction immortal. If an account is reaped and a user re-funds the account, then they could replay an immortal transaction. Always default to using a mortal extrinsic.
{% endhint %}

> \*The nonce queried from the System module does not account for pending transactions. You must track and increment the nonce manually if you want to submit multiple valid transactions at the same time.

Each transaction will have its own (or no) parameters to add. For example, the `transferKeepAlive` function from the Balances pallet will take:

`dest`: Destination address&#x20;

`#[compact] value`: Number of tokens (compact encoding)&#x20;

#### Serialized transaction format

Before being submitted, transactions are serialized. Serialized transactions are hex-encoded SCALE-encoded bytes. The Mandala Chain runtimes are upgradable; therefore, any interfaces are subject to change; the metadata allows developers to structure any extrinsic or storage entries accordingly. This being said, the serialization format can be described as follows:

* Compact encoded number of SCALE encoded bytes following this.&#x20;
* 1 bit: it is a 0 if no signature is present or a 1 if it is.&#x20;
* 7 bits: the extrinsic version, is equal to 4 in decimal.&#x20;
* 4 bytes: Spec version of the runtime.&#x20;
* 4 bytes: Transaction version of the runtime.&#x20;
* 32 bytes: Genesis hash of the chain.&#x20;
* 32 bytes: Block hash serving as the era reference. If the transaction is immortal, then this would be the genesis hash.
* If there is a signature:&#x20;
  * a SCALE encoded `sp_runtime::MultiAddress::Id<AccountId32, u32>` indicating the signer(s) of the transaction.&#x20;
  * a SCALE encoded `sp_runtime::MultiSignature::{SigningScheme}` with the signature\*.&#x20;
  * a SCALE encoded `sp_runtime::generic::Era` indicating how long this transaction is valid:&#x20;
    * If the transaction is immortal, the Era would be simply `0`.&#x20;
    * Otherwise, it would be a `Vec[u64, u64]` comprising the period and the phase.&#x20;
  * Compact encoded `u32` with the _nonce_.&#x20;
  * Compact encoded `u128` with the tip paid to the block producer.&#x20;
  * a SCALE encoded `sp_runtime::traits::SignedExtension<Vec<Text>>` with the additional data and logic associated with this transaction.&#x20;
* The specific transaction parameters, or call data, consist of the following:&#x20;
  * 1 byte: the pallet index the transaction is calling into.&#x20;
  * 1 byte: the function in the pallet the transaction is calling.&#x20;
  * Variable: the SCALE-encoded parameters required by the function being called.&#x20;

The metadata provides you with all the information required to construct the serialized call data specific to your transaction. You can read more about the metadata, its format, and how to get it in the Substrate documentation.

> \*Mandala Chain supports sr25519, ed25519, and ECDSA as signing schemes.

Once you have all the necessary information, you will need to:

1. Construct an unsigned transaction.&#x20;
2. Create a signing payload.&#x20;
3. Sign the payload.&#x20;
4. Serialize the signed payload into a transaction.&#x20;
5. Submit the serialized transaction.&#x20;

## Transfers

### Transferring Asset Balances

Users have a simple interface, namely the ability to transfer asset or token balances to other accounts on-chain. As mentioned before, if the asset is insufficient, the destination account must already exist for the transfer to succeed.&#x20;

The chain also contains a `transfer_keep_alive` function, similar to the Balances pallets, that will fail if execution kills the sending account.

