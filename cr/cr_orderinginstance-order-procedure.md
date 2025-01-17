---

copyright:

  years:  2022, 2023

lastupdated: "2023-04-24"

keywords: cyber recovery order procedure, order procedure cyber recovery, cyber recovery order instance, order cyber recovery, order cyber recovery instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Procedure to order Cyber Recovery
{: #cr_orderinginstance-order-procedure}

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click the **Cyber Recovery** card in the **Solutions** section. {: #step-1}
1. On the **Cyber Recovery** page, under **General Information**, select the instance configuration.
   * If you want to create a new configuration, select **New configuration**.
   * If you want to update a saved configuration or create a new configuration based on a saved one, select a saved configuration.
1. Accept or change the default **Instance name**.
1. The default name for the resource group is **Default**. Consider how you’d like to organize the resources in your account. You cannot change the resource group after the Cyber Recovery environment is created. For more information, see [Managing resource group](/docs/account?topic=account-rgs&interface=ui).
1. Select the instance type.
   * Click **Primary instance** to deploy a single instance in the environment or to deploy the first instance in a multisite topology.
   * Click **Secondary instance** to connect the instance with an existing (primary) instance in the environment for high availability. Select the primary instance that you want the secondary instance to be connected with, then enter the Cyber Recovery Administrator password for the primary instance.
1. Use the IBM-provided licenses for VMware components by selecting **Include with purchase**. For NSX, specify the license edition.

   Bring Your Own License (BYOL) is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide** and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.
   {: important}

1. In the **Consolidated cluster** section, accept or change the default cluster name **_instance name_-consolidated**. For more information, see [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-cluster-name).
1. For the data center location, select the **Geography**, **Data Center**, and **Pod** to host the clusters. For more information, see [Data center location](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-dc-location).
1. For the CPU generation, select either **Cascade Lake** or **SAP-certified**.
1. Select the **CPU model** and **RAM**.
1. Select the number of bare metal servers. You can select 3 - 20 bare metal servers.
1. If you want to use **NFS storage**, select the corresponding option.
   1. To add and configure file shares individually, toggle the **Configure shares individually** switch on. You must select at least one file share. Then, click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share.
   1. To add and configure the same settings to all file shares, specify the **Number of shares** and then, select the **Size (GB)** and **Performance** for all the shares.
1. If you want to use **vSAN™ storage**, select the corresponding option.
   1. Select the size for and number of **vSAN capacity disks**.
   1. Select the size for and number of **vSAN cache disks**.
   1. Select the box if you want to **Enable vSAN deduplication and compression**.
   1. For the **vSAN license**, select if you want to include and pay for a vSAN license with your order or provide your own license.
   1. If you choose to pay for a license, select an option from the menu.
1. Select the **Networking type**, either **Public and private network** or **Private network only**.
1. Select the **Uplink speed**. The 25 Gb option is available only for Cascade Lake servers and specific data centers.
1. To order new public and private VLANs, select **Order new VLANs**. A new public VLAN and two private VLANs are provisioned.
   * To reuse existing public and private VLANs, if they are available, select **Select existing VLANs**. Specify the VLANs and the subnets.
   * For new orders, you can select **Order new VLANs** only.
   * If the consolidated or management cluster and the workload clusters are in the same location, you cannot use existing VLANs. Instead, the workload clusters reuse the VLANs from the management cluster.
1. If you want a workload cluster, toggle the **Deploy separate workload cluster** switch on and specify the cluster settings.
   1. Accept or change the default **Cluster name** of the workload cluster.
   1. For the **Data center location**, select the **Geography**, **Data Center**, and **Pod** to host the clusters. For more information, see [Data center location](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-dc-location).
   1. For **CPU generation**, select either **Cascade Lake** or **SAP-certified**.
   1. Select the **CPU model** and **RAM**.
   1. Select the **number of bare metal servers**. You can select 2 - 20 bare metal servers.
1. If you want to use **NFS storage**, select the corresponding option.
   1. To add and configure file shares individually, toggle the **Configure shares individually** switch on. You must select at least one file share. Then, click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share.
   1. To add and configure the same settings to all file shares, specify the **Number of shares** and select the **Size (GB)** and **Performance** for all the shares.
1. If you want to use **vSAN storage**, select the corresponding option.
   1. Select the size for and number of **vSAN capacity disks**.
   1. Select the size for and number of **vSAN cache disks**.
   1. Select the box if you want to **Enable vSAN deduplication and compression**.
   1. For the **vSAN license**, select if you want to include and pay for a vSAN license with your order or provide your own license.
   1. If you choose to pay for a license, select an option from the menu.
1. Select the **Networking type**, either **Public and private network** or **Private network only**.
1. Select the **Uplink speed**. The 25 Gb option is available only for Cascade Lake servers and specific data centers.
1. To order new public and private VLANs, select **Order new VLANs**. A new public VLAN and two private VLANs are provisioned.
   1. To reuse existing public and private VLANs, if they are available, select **Select existing VLANs**. Specify the VLANs and the subnets.
   2. For new orders, you can select **Order new VLANs** only.
   3. If the consolidated or management cluster and the workload clusters are in the same location, you cannot use existing VLANs. Instead, the workload clusters reuse the VLANs from the management cluster.
1. Choose the firewall appliance for your instance and follow the steps, depending on your selection:
   1. For **Gateway cluster with Juniper® vSRX**, **Gateway cluster with FortiGate® Virtual Appliance**, and **Bring your own gateway appliance**, specify the gateway [cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-cr-orderinginstance-edge#cr-orderinginstance-edge-cluster-name), the CPU model, the RAM size, the uplink speed, and the networking type.
   1. For **Gateway cluster with Juniper vSRX** and **Gateway cluster with FortiGate Virtual Appliance**, you must also specify the corresponding service settings in a later step.
   1. For **FortiGate Security Appliance**, you must order the **FortiGate Security Appliance 10 Gbps** service from the [IBM Cloud catalog](https://cloud.ibm.com/catalog/infrastructure/fortigate-security-appliance-10gb). Confirm that you ordered the service and continue with the following steps.
1. Complete the information for the **Gateway cluster**.
   1. Accept or change the default **Cluster name** of the gateway cluster.
   1. For **Compute capacity**, the values are:
      * Clusters hosts: 2
      * Storage: 2 * 3.8 TB SSD
   1. Select the **CPU model** and **RAM**.
   1. Select the **Uplink speed**. 25 Gb is available only for Cascade Lake servers and specific data centers. For more information, see [Uplink speed](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-edge-gateway-cluster#vc_orderinginstance-edge-cluster-uplink).
   1. Select the **Networking type**, either **Public and private network** or **Private network only**.
1. Complete the information for the **Network interface**.
   1. Enter the **Hostname prefix** and the root **Domain name** for the instance that you are creating.
   1. Specify the **DNS configuration**.
   1. Under **Network diagram**, you can customize the hostnames prefix individually by selecting **Configure hostnames individually**.
1. The **Add-on services** section lists the various services that you can order for your Cyber Recovery instance.
    * The **Included services** category lists the services that are included in your Cyber Recovery order.
    * The **Recommended services** category lists the services that IBM recommends to fully use your resources.
    * You can open each of the remaining categories to select more services.

For more information, see [Add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addon-services).

## Related Links
{: #cr_orderinginstance-order-procedure-related-links}

* [Adding clusters to Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingclusters)
* [Expanding and contracting capacity](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingservers)
