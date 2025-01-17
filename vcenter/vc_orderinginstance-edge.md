---

copyright:

  years:  2016, 2022

lastupdated: "2022-03-21"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Gateway cluster
{: #vc_orderinginstance-edge-gateway-cluster}

Select the **Gateway cluster** checkbox to order a dedicated cluster for the network edge and the firewall components that are required for the Juniper® vSRX service. The gateway cluster is deployed in the same data center as the consolidated cluster.

The data center of the consolidated cluster must be available for gateway cluster deployment. Gateway cluster deployment is not supported for **Dallas 09**.
{: note}

## Cluster name
{: #vc_orderinginstance-edge-cluster-name}

The cluster name must meet the requirements that are listed in [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-consoldworkldcluster-settings#vc_orderinginstance-consoldworkldcluster-cluster-name).

## CPU model
{: #vc_orderinginstance-edge-cluster-cpu}

You can choose the following CPU models:
* Dual Intel® Xeon® Silver 4210 processor (Cascade Lake)
* Dual Intel Xeon Gold 5218 processor (Cascade Lake)

## RAM
{: #vc_orderinginstance-edge-cluster-ram}

You can select different values between 64 GB and 1.5 TB.

## Number of bare metal servers
{: #vc_orderinginstance-edge-cluster-bare-metal}

The number of servers is set to two and cannot be changed. Both servers have the same configuration.

## Uplink speed
{: #vc_orderinginstance-edge-cluster-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## Networking type
{: #vc_orderinginstance-edge-cluster-private-nics}

Select either **Public and private network** or **Private network only** for the gateway cluster.

## Related links
{: #vc_orderinginstance-edge-related}

* [Network interface](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-network-interface-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
