# Network RPC endpoints

## What is RPC Node?[​](https://docs.astar.network/docs/build/environment/endpoints#what-is-rpc-node) <a href="#what-is-rpc-node" id="what-is-rpc-node"></a>

* RPC nodes can be queried for information and used to initiate transactions.
* The purpose of RPC nodes is to allow decentralized applications and clients to communicate with a Blockchain network.
* RPC nodes listen for requests, respond with the necessary data, or execute the requested transaction.
* Common usage of RPC nodes includes querying the Blockchain for information, sending transactions, and executing smart contract functions.
* RPC nodes are important for decentralized applications to function and interact with a Blockchain network, allowing for decentralized exchange and other use cases.

## Public Endpoints <a href="#public-endpoints" id="public-endpoints"></a>

> INFO
>
> The free endpoints below are dedicated to end users, they can be used to interact with dApps or deploy/call smart contracts.
>
> They limit the rate of API calls, so they are not suitable for high demand, such as a dApp UI constantly scraping blockchain data or an indexer.

> TIP
>
> To meet the demands of a production dApp, we provide you with our integration layer called Dhatu. Please refer to [Dhatu](../integration-layer.md) documentation for more details.



{% tabs %}
{% tab title="Mandala" %}
<table><thead><tr><th width="241"></th><th>Public endpoint Mandala</th></tr></thead><tbody><tr><td>Network</td><td>Mandala Chain </td></tr><tr><td>HTTPS</td><td>node1.mandalachain.io</td></tr><tr><td>WebSocket</td><td>wss://node1.mandalachain.io</td></tr><tr><td>Symbol</td><td>KPG</td></tr></tbody></table>
{% endtab %}
{% endtabs %}
