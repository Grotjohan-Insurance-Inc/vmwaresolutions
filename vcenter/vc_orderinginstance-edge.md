---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Edge services cluster
{: #vc_orderinginstance-edge-services-cluster}

Select the **Edge services cluster** checkbox to order a dedicated cluster for the network edge and the firewall components that are required for the Juniper® vSRX service. The edge services cluster is deployed in:
* For VMware NSX-T® - the consolidated cluster
* For VMware NSX-V - the same data center as the instance

Review the following restrictions for edge services clusters:
* The data center of the consolidated cluster (for NSX-T) or the instance (for NSX-V) must be available for edge services cluster deployment. Edge services cluster deployment is not supported for **Dallas 09** and **Hong Kong 02**.
* You cannot add more than one edge services cluster in the same data center pod. If you add multiple edge services clusters in the same pod, the clusters would share a transit VLAN, which might cause subsequent issues with the Juniper vSRX installation.

## Cluster name
{: #vc_orderinginstance-edge-cluster-name}

The cluster name must meet the requirements that are listed in [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance#vc_orderinginstance-cluster-name).

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

## Networking type
{: #vc_orderinginstance-edge-cluster-private-nics}

Select either **Public and private network** or **Private network only** for the edge services cluster.

## Related links
{: #vc_orderinginstance-edge-related}

* [Network interface settings](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-network-interface-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)