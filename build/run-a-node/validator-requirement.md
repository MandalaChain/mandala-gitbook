---
hidden: true
---

# Validator Requirement

## How to become a validator <a href="#how-to-become-a-collator" id="how-to-become-a-collator"></a>

### Permissioned validator[​](https://docs.astar.network/docs/build/nodes/collator/requirements#permissionless-collator) <a href="#permissionless-collator" id="permissionless-collator"></a>

To become a permissionless collator on Mandala Chain networks, you need to meet the requirements below.

**Collator staking requirements**

{% tabs %}
{% tab title="Utama Mandala (Mainnet)" %}
* Bond: 3,200,000 KPG tokens (3.2M $KPG)
* Meet hardware requirements
{% endtab %}

{% tab title="Garbha Mandala (Testnet)" %}
* Bond: 3,200,000 KPGT tokens (3.2M $KPGT)
* Meet hardware requirements
{% endtab %}
{% endtabs %}

If your node stops producing blocks for one session, your node will be kicked out of the active set, and 1% of the bonded funds will be slashed. Running a node with low performance can lead to skipping blocks, which can lead to being kicked out of the active set.

> TIP
>
> Set your collator with: **Extrinsics - CollatorSelection - Register as candidate** | Onboarding takes **n+1** session.

#### System requirements[​](https://docs.astar.network/docs/build/nodes/collator/requirements#system-requirements) <a href="#system-requirements" id="system-requirements"></a>

A collator deploys its node on a remote server. You can choose your preferred provider for dedicated servers and operating systems. Generally speaking, we recommend you select a provider/server in your region. This will increase the decentralization of the network. You can choose your preferred operating system, though we highly recommend Linux.

**Hardware requirements**

Use the charts below to find the basic configuration, guaranteeing that all blocks can process in time. If the hardware doesn't meet these requirements, there is a high chance it will malfunction, and you risk being automatically **kicked out and slashed** from the active set.

> CAUTION
>
> Ensure your server is a **bare metal only dedicated to the collator node**; any unnecessary process running on it will significantly decrease the collator performance. **We strongly discourage using a VPS** to run a collator because of their low performance.
>
> Collators are the nodes which require the most powerful hardware because they have short time frames to assemble a block and collate it to the relay chain. To run a collator, it is necessary to use a **CPU of a minimum 4 Ghz per core** and an **NVMe SSD disk** (SATA SSDs are unsuitable for collators because they are too slow).

{% tabs %}
{% tab title="Utama" %}
<table><thead><tr><th width="232">Component</th><th>Requirement</th></tr></thead><tbody><tr><td>System</td><td>Ubuntu 20.04</td></tr><tr><td>CPU</td><td>8 cores</td></tr><tr><td>Memory</td><td>16 GB</td></tr><tr><td>Hard Disk</td><td>500 GB SSD (NVMe preferable)</td></tr></tbody></table>
{% endtab %}

{% tab title="Garbha" %}
| Component | Requirement                  |
| --------- | ---------------------------- |
| System    | Ubuntu 20.04                 |
| CPU       | 4 cores                      |
| Memory    | 8 GB                         |
| Hard Disk | 200 GB SSD (NVMe preferable) |
{% endtab %}
{% endtabs %}

## Ports[​](https://docs.astar.network/docs/build/nodes/archive-node/#ports) <a href="#ports" id="ports"></a>
