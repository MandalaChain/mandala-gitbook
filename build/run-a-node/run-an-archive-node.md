---
hidden: true
---

# Run an Archive Node

## Overview <a href="#overview" id="overview"></a>

An **archive node** stores the history of past blocks. Most of the time, an archive node is used as an **RPC endpoint**. RPC plays a vital role in our network: it connects users and dApps to the blockchain through WebSocket and HTTP endpoints. For example, our public endpoints

```
node1.mandalachain.io
wss://node1.mandalachain.io
```

run archive nodes for anyone to connect to the Mandala Chain quickly.

**DApp projects** must run their own RPC node as an archive to retrieve necessary blockchain data and not rely on public infrastructure. Public endpoints respond slower because of the large amount of users connected and are rate-limited.

> CAUTION
>
> Be careful not to confuse with a **full node** that has a pruned database: a full node only stores the current state and most recent blocks (256 blocks by default) and uses much less storage space.

We maintain two different networks: Madya mainnet and Niskala testnet.

| MandalaChain | Token          | Ticker |
| ------------ | -------------- | ------ |
| Madya        | Kepeng         | KPG    |
| Niskala      | Kepeng Testnet | KPGT   |

## Requirements[​](https://docs.astar.network/docs/build/nodes/archive-node/#requirements) <a href="#requirements" id="requirements"></a>

### Machine <a href="#machine" id="machine"></a>

{% tabs %}
{% tab title="Madya (Mainnet)" %}
| Component | Requirement                  |
| --------- | ---------------------------- |
| System    | Ubuntu 20.04                 |
| CPU       | 8 cores                      |
| Memory    | 16 GB                        |
| Hard Disk | 500 GB SSD (NVMe preferable) |
{% endtab %}

{% tab title="Niskala (Testnet)" %}
| Component | Requirement                  |
| --------- | ---------------------------- |
| System    | Ubuntu 20.04                 |
| CPU       | 4 cores                      |
| Memory    | 8 GB                         |
| Hard Disk | 200 GB SSD (NVMe preferable) |
{% endtab %}
{% endtabs %}

## Ports[​](https://docs.astar.network/docs/build/nodes/archive-node/#ports) <a href="#ports" id="ports"></a>

The Mandala Chain node will listen at different ports by default for both the mainnet and the testnet.

| Description | Testnet Port | Custom Port Flag    |
| ----------- | ------------ | ------------------- |
| P2P         | 30333        | `--port`            |
| RPC         | 9944         | `--rpc-port`        |
| Prometheus  | 9615         | `--prometheus-port` |

For all types of nodes, ports `30333` and `30334` need to be opened for incoming traffic at the Firewall. **Validator nodes should not expose WS and RPC ports to the public.**

## Installation[​](https://docs.astar.network/docs/build/nodes/archive-node/#installation) <a href="#installation" id="installation"></a>

There are 2 different ways to run a Mandala Chain node:

Using [Binary](https://docs.astar.network/docs/build/nodes/archive-node/binary) - run the node from a binary file and set it up as `systemd` service

Using [Docker](https://docs.astar.network/docs/build/nodes/archive-node/docker) - run the node within a Docker container
