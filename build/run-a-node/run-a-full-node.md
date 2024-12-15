---
hidden: true
---

# Run a Full Node

## Overview[​](https://docs.astar.network/docs/build/nodes/full-node#overview) <a href="#overview" id="overview"></a>

Running a full node on a MandalaChain chain allows you to connect to the network, sync with a bootnode, obtain local access to RPC endpoints, author blocks on the parachain, and more.

Different from the archive node, a full node discards all finalized blocks older than the configured number of blocks (256 blocks by default). A full node occupies less storage space than an archive node because of pruning.

A full node may eventually be able to rebuild the entire chain with no additional information and become an archive node, but at the time of writing, this is not implemented. If you need to query historical blocks past that you have pruned, you need to purge your database and resync your node, starting in archive mode. Alternatively, you can use a backup or snapshot of a trusted source to avoid needing to sync from genesis, thus only requiring the blocks past that snapshot.

If your node needs to provide old historical blocks' data, please consider using the [Archive node](run-an-archive-node.md) instead.

### Requirements[​](https://docs.astar.network/docs/build/nodes/full-node#requirements) <a href="#requirements" id="requirements"></a>

Requirements for running any node are similar to what we recommend for the Archive node. Read more about this [here](run-an-archive-node.md). Note that the Full node requires less disk space. The hard disk requirement for the Archive node is not applied to Full nodes.

To set a full node, you need to specify the number of blocks to be pruned:

```
--pruning 1000 \
```
