# Network Communication

## What is libp2p?

[Libp2p](https://libp2p.io/) is a modular and extensible networking stack that is used by IPFS, Substrate, and many other projects. It is a collection of peer-to-peer protocols for finding peers and connecting to them. Its modules have logic for content routing, peer routing, peer discovery, different transports, and NAT traversals. It is intended to be used by applications for building large-scale peer-to-peer networks by only selecting the parts of the protocol suite that are needed.

The Rust implementation of the specification was built and primarily maintained by a team of contributors at Parity Technologies. The Go and JavaScript versions are maintained by Protocol Labs as well as community contributors. A Nim (programming language) version of the library also exists. Libp2p, as a whole, is an open-source project that is actively developed and expanded on various code repositories hosted on [their GitHub](https://github.com/libp2p).

## Does Mandala Chain use libp2p?&#x20;

Yes, since the Mandala Chain is built with Substrate. Substrate uses a networking protocol based on libp2p (specifically the Rust libp2p library). However, Substrate uses a mix of standard libp2p protocols and protocols that are homegrown and not official libp2p standards. Of the standard protocols, those that are shared with other implementations of libp2p, such as IPFS, are connection-checking (ping), asking for information on a peer (identity), and Kademlia random walks (kad).

Of the protocols that are custom to Substrate, there is the legacy Substrate stream, a request-response for getting information on blocks (sync), a light client protocol, a notification protocol for transactions, and block announcement. For detailed information on how Substrate uses libp2p and the standard and custom protocols, please see the [networking documentation](https://paritytech.github.io/polkadot-sdk/master/sc_network/index.html) by Parity Technologies.

## How does libp2p differ from IPFS?&#x20;

The [Interplanetary File System](https://ipfs.tech/) (IPFS) is a peer-to-peer hypermedia protocol used primarily for storing files. It allows one to upload a file onto the network and share it with its content addressable URI. IPFS, like Substrate, is an application of libp2p and exists higher on the technology stack. Although both IPFS and Substrate use libp2p, it cannot be said that Substrate "uses" IPFS since, besides sharing the underlying library for networking, there is no native integration between the two applications.
