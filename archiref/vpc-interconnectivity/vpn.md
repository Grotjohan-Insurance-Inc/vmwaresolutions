---

copyright:

  years:  2022

lastupdated: "2022-12-29"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} VPN overview
{: #interconnectivity-vpn}

{{site.data.keyword.cloud}} {{site.data.keyword.vpn_vpc_full}} service offers two types of VPNs:
* **Site-to-site gateways** - This VPN type connects your on-premises network to the {{site.data.keyword.vpc_short}} network.
* **Client-to-site servers** - This VPN type allows clients on the internet to connect to VPN servers, while still maintaining secure connectivity.

{{site.data.keyword.cloud_notm}} VPN Gateway for VPC provides a simple yet powerful solution for highly scalable and robust site-to-site VPN gateways. With this service, you can create site-to-site VPN tunnels for secure, encrypted connectivity. Also, you connect from on-premises sites to {{site.data.keyword.cloud_notm}} through a VPN gateway on an {{site.data.keyword.vpc_short}}, and a peer gateway on-premises. For more information, see [About site-to-site VPN gateways](/docs/vpc?topic=vpc-using-vpn).

{{site.data.keyword.cloud_notm}} Client {{site.data.keyword.vpn_vpc_short}} provides an open source compatible client-to-site VPN solution that allows users to connect to {{site.data.keyword.cloud_notm}} resources through secure, encrypted connections. Whether you want to connect to access or manage your workloads that are running in VPC Virtual Servers or VMware® workloads, you can use the OpenVPN-based client-to-site VPN solution for remote access. For more information, see [About client-to-site VPN servers](/docs/vpc?topic=vpc-vpn-client-to-site-overview).

## Considerations with roll-your-own VMware solution in VPC
{: #interconnectivity-vpn-ryo-considerations}

When you use the VMware virtual machines (VMs) on VPC subnets architecture, your VMs are attached to VPC subnets and the routing behaves in the same way as with VPC Virtual Servers. The VPC subnets are provisioned from the zone prefix, and the routing works between the VPC without any required changes. You can use both {{site.data.keyword.cloud_notm}} VPN Gateway for VPC and {{site.data.keyword.cloud_notm}} Client {{site.data.keyword.vpn_vpc_short}} with this solution as described in the documentation previously listed.

![VPNaaS with VMware on VPC](../../images/vpc-ryo-diagrams-dl-sub-arch.svg "VPNaaS with VMware on VPC"){: caption="Figure 1. VPNaaS with VMware on VPC" caption-side="bottom"}

When you use NSX-T™ on your VMware solution on VPC, the VMs are attached on the NSX-T overlay segments. They use an IP address range or prefix, which is reachable through VPC route that points to NSX-T Tier-0 private uplink VIP as described in the [VMware NSX-T logical routing on VPC](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-ryo-nsx-t-vpc-routing) topic. You can use both {{site.data.keyword.cloud_notm}} VPN Gateway for VPC and {{site.data.keyword.cloud_notm}} Client {{site.data.keyword.vpn_vpc_short}} with this solution as described in the documentation previously listed.

![VPNaaS with VMware on VPC with NSX-T](../../images/vpc-ryo-diagrams-dl-nsx-t-arch.svg "VPNaaS with VMware on VPC with NSX-T"){: caption="Figure 2. VPNaaS with VMware on VPC with NSX-T" caption-side="bottom"}

When you use {{site.data.keyword.cloud_notm}} Client {{site.data.keyword.vpn_vpc_short}}, you must add VPN routes that are advertised to the VPN clients for the NSX-T overlay destinations. Set the VPC routes to the same destination and pointing to the NSX-T Tier-0 Private Uplink VIP. In NSX-T Tier-0, ensure that you have a static route for your VPN Client IPv4 address pool prefix route that points to the default gateway of the uplink subnet.

With {{site.data.keyword.cloud_notm}} VPN Gateway for VPC, it is recommended to use routed-based tunnels, as described in the [VPN Gateway for VPC features](/docs/vpc?topic=vpc-using-vpn#vpn-features) topic. Ensure that you define static routes at the on-premises VPN gateway toward NSX-T overlay prefixes. Set the VPC routes to the same destination and pointing to the NSX-T Tier-0 Private Uplink VIP. For on-premises destinations, VPC routes must point to the VPN Tunnel. In NSX-T Tier-0, ensure that your private routes are pointing to the default gateway of the uplink subnet.

## Related links
{: #interconnectivity-vpn-ryo-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} Bare Metal Servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vpc-ryo-overview)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on Bare Metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
