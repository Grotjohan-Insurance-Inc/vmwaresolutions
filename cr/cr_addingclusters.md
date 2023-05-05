---

copyright:

  years:  2022, 2023

lastupdated: "2023-04-24"

keywords: cyber recovery add clusters, add cluster, cyber recovery cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Adding clusters to Cyber Recovery instances
{: #cr_addingclusters}

You can add clusters to Cyber Recovery instances to expand the compute and storage capacity. Within a cluster, you can manage VMware ESXi™ servers for better resource allocation and high availability.

## Before you add clusters to Cyber Recovery instances
{: #cr_addingclusters-before}

* Whenever possible, add clusters by using the {{site.data.keyword.vmwaresolutions_full}} console and not the VMware vSphere® Web Client. Changes that you make on the vSphere Web Client are not synchronized with the VMware Solutions console. If you want to add clusters to Cyber Recovery instances by using the vSphere Web Client, do so only for on-premises clusters or clusters that you don't manage in the VMware Solutions console.
* The number of clusters, hosts, and virtual machines (VMs) determines the maximum limit for the number of clusters you can add. You must remain within the VMware® sizing guidelines and limits for your deployment. For more information about maximum limits, see [VMware Configuration Maximums](https://configmax.vmware.com/home){: external}.
* You can add or delete a cluster while another cluster is being created or deleted.

## Cluster type
{: #cr_addingclusters-cluster-type}

Select the cluster type, either **Workload cluster** or **Gateway cluster**.

## System settings for workload clusters
{: #cr_addingclusters-sys-settings-workload}

When you add a workload cluster to a Cyber Recovery instance, you must specify the following settings.

### Cluster name
{: #cr_addingclusters-cluster-name}

The cluster name is set to **vcs-lj-workload_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

{{site.data.content.cluster-name-requirements-list}}

### Licensing settings
{: #cr_addingclusters-licensing-settings}

Review the following information and specify the licensing setting for the Cyber Recovery component in the cluster.
* For Business Partner users, the vSphere license (Enterprise Plus edition) is included and purchased on your behalf.
* For users who are not Business Partners, use the IBM-provided VMware licenses for this component, which are included with purchase.

Bring Your Own License (BYOL) is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide** or **Use existing license** and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.
{: important}

* The **Use existing license** option is available only if you are using a BYOL vSphere license for your instance. When the option is enabled, you can select the existing license only if the instance has enough capacity for the additional hosts.

### Bare metal server settings
{: #cr_addingclusters-bare-metal-settings}

Options might differ depending on the version that your instance was initially deployed in. You can choose between the **Cascade Lake** or **SAP-certified** server types.

#### Data center location
{: #cr_addingclusters-dc-location}

The {{site.data.keyword.cloud_notm}} data center location of the cluster is set to the {{site.data.keyword.cloud_notm}} data center of the Cyber Recovery instance by default. You can deploy the cluster to a different {{site.data.keyword.cloud_notm}} data center than the deployed instance if you ensure that the network latency between the two {{site.data.keyword.cloud_notm}} data centers is less than 150 ms. To check the network latency, you can use a tool such as [Looking Glass](http://lg.softlayer.com/){: external}.

If you deploy the cluster to a different {{site.data.keyword.cloud_notm}} data center or {{site.data.keyword.cloud_notm}} infrastructure pod, three extra VLANs are ordered for use with the ordered {{site.data.keyword.cloud_notm}} bare metal servers.

#### Cascade Lake
{: #cr_addingclusters-cascade}

{{site.data.content.cascade-para-intro}}

| CPU model     | Cores     | GHz     | RAM sizes   |
|:------------- |:----------|:--------|:----------- |
| Dual Intel Xeon Silver 4210 processor | 20 | 2.2 | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor | 32 | 2.3 | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor | 40 | 2.5 | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 processor | 16 | 3.9 | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor | 48 | 2.4 | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor | 80 | 2.5 | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor | 96 | 2.4 | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 1. Options for Cascade Lake bare metal servers - NSX-T instances" caption-side="bottom"}
{: class="simple-tab-table"}
{: tab-title="NSX-T instances"}
{: tab-group="Cascade Lake Intel servers"}
{: #simpletabtable-cascade-nsxt}

#### SAP-certified
{: #cr_addingclusters-sap}

{{site.data.content.sap-para-intro}}

| CPU model     | Cores     | GHz     | RAM sizes   |
|:------------- |:----------|:--------|:----------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW192) | 32 | 2.3 | 192 GB |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW384) | 32 | 2.3 | 384 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.NW768) | 40 | 2.5 | 768 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.NW768_v2) | 48 | 2.4 | 768 GB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW1500) | 56 | 2.7 | 1.5 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW3000) | 56 | 2.7 | 3 TB |
{: caption="Table 2. Options for SAP-certified bare metal servers - NetWeaver" caption-side="bottom"}
{: class="simple-tab-table"}
{: tab-title="NetWeaver"}
{: tab-group="SAP-certified Intel servers"}
{: #simpletabtable-sap-netweaver}


| CPU model     | Cores     | GHz     | RAM sizes |
|:------------- |:----------|:--------|:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.H2.192) | 32 | 2.3 | 192 GB |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.H2.384) | 32 | 2.3 | 384 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.H2.768) | 40 | 2.5 | 768 GB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.H2.1500) | 56 | 2.7 | 1.5 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.H2.3000) | 56 | 2.7 | 3 TB |
| Quad Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.H4.3000) | 112 | 2.7 | 3 TB |
| Quad Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.H4.6000) | 112 | 2.7 | 6 TB |
{: caption="Table 2. Options for SAP-certified bare metal servers - HANA" caption-side="bottom"}
{: tab-title="HANA"}
{: tab-group="SAP-certified Intel servers"}
{: class="simple-tab-table"}
{: #simpletabtable-sap-hana}

#### Number of bare metal servers
{: #cr_addingclusters-bare-metal-number}

* All servers that you order have the same configuration.
* For NFS storage, you can order 2-59 servers. However, for production workloads, a minimum of 3 servers is recommended.
* For vSAN™ storage, you can order 4-59 servers.

### Storage settings
{: #cr_addingclusters-storage-settings}

Storage settings are based on your selection of {{site.data.keyword.cloud_notm}} bare metal server configuration and the storage type.

You can add NFS storage shares to an existing vSAN or NFS cluster.
{: note}

#### vSAN storage
{: #cr_addingclusters-vsan-storage}

Specify the following vSAN options.

##### Size for vSAN capacity disks
{: #cr_addingclusters-vsan-capacity-size}

Select an option for the capacity disks that you need.

##### Number of vSAN capacity disks
{: #cr_addingclusters-vsan-capacity-number}

Specify the number of capacity disks that you want to add.

##### Size for vSAN cache disks
{: #cr_addingclusters-vsan-cache-size}

Review the **Size for vSAN cache disks** value.

##### Number of vSAN cache disks
{: #cr_addingclusters-vsan-cache-number}

Review **Number of vSAN cache disks**. The value depends on whether you checked the **High performance with Intel Optane** box.

##### Enable vSAN deduplication and compression
{: #cr_addingclusters-vsan-storage-enable-comp}

vSAN storage depends on the number of servers and your total disk capacity, and the use of deduplication and compression.

The amount of storage reduction from deduplication and compression depends on many factors, including the type of data stored and the number of duplicate blocks. Larger disk groups tend to provide a higher deduplication ratio. For more information, see [Using deduplication and compression](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.vsan.doc/GUID-3D2D80CC-444E-454E-9B8B-25C3F620EFED.html){: external}.
{: note}

##### vSAN license
{: #cr_addingclusters-vsan-storage-lic}

Use the IBM-provided VMware license for the vSAN component, which is included with purchase.

Bring Your Own License (BYOL) is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide** or **Use existing license** and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.
{: important}

The **Use existing license** option is available only if you are using a BYOL vSAN license for your instance. When the option is enabled, you can select the existing license only if the instance has enough capacity for the additional hosts.

If your initial cluster was a vSAN cluster, any additional vSAN clusters use the same vSAN license and have the same configuration as the initial one. This behavior is also true if any cluster (initial or additional) in the instance has vSAN chosen to be deployed on it. The first time you're prompted for the vSAN license (BYOL or purchased) and the edition. The next time that you select vSAN for a new cluster, the license that was chosen initially is reused.

#### NFS storage
{: #cr_addingclusters-nfs-storage}

When you select **NFS storage**, you can add file-level shared storage for your instance where all shares use the same settings or you can specify different configuration settings for each file share. The number of file shares must be in the range 1-100.

Specify the following NFS options.
* **Configure shares individually** - Toggle this switch on to specify different configuration settings for each file share.
* **Number of shares** - When want to use the same configuration setting for each file share, specify the number of file shares for the NFS shared storage that you want to add.
* **Size (GB)** - Select the capacity that meets your shared storage needs.
* **Performance** - Select the IOPS (input/output operations per second) per GB based on your workload requirements.
* **Add shared storage** - Select to add individual file shares with different configuration settings.

The following table indicates the performance level details.

| Option        | Details       |
|:------------- |:------------- |
| 0.25 IOPS/GB | This option is designed for workloads that are not used often. Example applications include vaulted data, hosting large databases with legacy data, or virtual disk images of virtual memory system as backup. |
| 2 IOPS/GB | This option is designed for most general-purpose workloads. Example applications include hosting small databases, backing up web applications, or VM disk images for a hypervisor. |
| 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. Example applications include transactional databases. |
| 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. Example applications include high-transaction databases and other performance-sensitive databases. This performance level is limited to a maximum capacity of 4 TB per file share. |
{: caption="Table 3. NFS performance level options" caption-side="bottom"}

### Network interface settings
{: #cr_addingclusters-network-interface-settings}

When you add a cluster for a Cyber Recovery instance, you must specify the following network interface settings.

#### Hostname prefix
{: #cr_addingclusters-host-name}

You can use the default hostname prefix or specify a new one. When you specify a new hostname prefix, the hostname prefix must meet the following requirements:
- Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
- The hostname prefix must start with a lowercase alphabetic character.
- The hostname prefix must end with a lowercase alphabetic or numeric character.
- The maximum length of the hostname prefix is 10 characters.

#### Network diagram
{: #cr_addingclusters-network-diagram}

You can customize the hostnames prefix individually by selecting **Configure hostnames individually**. It must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* No consecutive dash characters are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.

#### Networking type
{: #cr_addingclusters-network}

Network interface card (NIC) enablement settings are based on your selection of either **Public and private network** or **Private network only**.

#### Uplink speed
{: #cr_addingclusters-uplink}

The **Uplink speed** option is not available to gateway clusters.
{: note}

{{site.data.content.uplink-speed-options-list}}

| Geography | Data center | Pod |
|:--------- |:----------- |:--- |
| Asia-Pacific | TOK02 | 02 |
| Asia-Pacific | TOK04 | 01 |
| Asia-Pacific | TOK05 | 01 |
| Europe | FRA02 | 02 |
| Europe | FRA05 | 01 |
| Europe | LON04 | 01 |
| Europe | LON06 | 01 |
| NA East | TOR04 | 01 |
| NA East | WDC04 | 05 |
| NA East | WDC06 | 01 |
| NA East | WDC07 | 01 |
| NA South | DAL10 | 03 |
| NA South | DAL12 | 01 |
| NA South | DAL13 | 02 |
{: caption="Table 4. Available locations for 25 Gb uplink speed" caption-side="bottom"}

#### VLANs
{: #cr_addingclusters-vlans}

Network settings are based on your selection of either **Order new VLANs** or **Select existing VLANs**.

One public VLAN and two private VLANs are required for your instance order. The two private VLANs are trunked into each {{site.data.keyword.cloud_notm}} bare metal server.

##### Order new VLANs
{: #cr_addingclusters-new-vlans}

Select to order one new public VLAN and two new private VLANs.

##### Select existing VLANs
{: #cr_addingclusters-existing-vlans}

Depending on the {{site.data.keyword.cloud_notm}} data center that you selected, existing public and private VLANs might be available.

When you select to reuse existing public and private VLANs, specify the VLANs and subnets:
* **Public VLAN** is for public network access. If you select the **Allocate a new one** option for this field, a new public VLAN is allocated automatically. This field is only available on the **Public and private network** tab.
* **Public primary subnet** is assigned to physical hosts for public network access. If you select the **Auto assigned** option for this field, a new public primary subnet is selected automatically, and a new one is created if necessary. This field is only available on the **Public and private network** tab.
* **Private VLAN** is for connectivity among the data centers and services within the {{site.data.keyword.cloud_notm}}. If you select the **Allocate a new one** option for this field, a new private VLAN is allocated automatically.
* **Private primary subnet** is assigned to physical hosts for management traffic. If you select the **Auto assigned** option for this field, a new private primary subnet is selected automatically, and a new one is created if necessary.
* **Secondary private VLAN** is for VMware features such as vSAN. You can select an existing secondary private VLAN or select to allocate a new one.

Ensure that the firewall configuration on the selected VLANs does not block the management data traffic. Also, ensure that all the VLANs that you select are in the same pod. ESXi servers cannot be provisioned on mixed-pod VLANs.
{: important}

Optionally, use **Advanced settings** to configure portable subnets for VLANs.

Use the **Public VLAN**, **Private VLAN**, or **Secondary private VLAN** tabs to specify the **Portable subnet** for each applicable purpose. If you select the **Allocate a new one** option for this field, a new portable subnet is allocated automatically.
**Notes**
* You must complete the **Public VLAN**, **Private VLAN**, or **Secondary private VLAN** settings before you can configure portable subnets.
* The number of portable subnets is displayed on the **Advanced settings** option after you save the portable subnet settings. Click **Portable subnets settings** to edit the settings.
* The saved portable subnet settings are cleared if you change the **Public VLAN**, **Private VLAN**, or **Secondary private VLAN** settings.

{{site.data.keyword.vmwaresolutions_short}} takes control of the entire subnet and you can't use any IP addresses in the subnet.
{: important}

## System settings for gateway clusters
{: #cr_addingclusters-sys-settings-edge}

When you add a gateway cluster to a Cyber Recovery instance, you must specify the following settings.

### Data center location
{: #cr_orderinginstance-dc-edge}

Select the {{site.data.keyword.cloud}} data center settings. For more information, see [Region and data center locations for resource deployment](/docs/overview?topic=overview-locations).

#### Geography
{: #cr_orderinginstance-dc-region-edge}

Select the region where your consolidated cluster or instance is hosted.

#### Data center
{: #cr_orderinginstance-dc-location-edge}

Select the {{site.data.keyword.cloud_notm}} data center where the consolidated cluster is hosted.

#### Pod
{: #cr_orderinginstance-dc-pod-edge}

Select the {{site.data.keyword.cloud_notm}} data center pod where you want to deploy your resources. Keep the default pod selection if you do not have reasons to prefer a different pod.

### Cluster name
{: #cr_addingclusters-cluster-name-edge}

By default, the cluster names are set to **_instance name_-edge**.

You can also specify a new name for your clusters. The names must meet the requirements that are listed in [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-consoldworkldcluster-settings#vc_orderinginstance-consoldworkldcluster-cluster-name).

### CPU model
{: #cr_addingclusters-edge-cluster-cpu}

You can choose the following CPU models:
* Dual Intel® Xeon® Silver 4210 processor (Cascade Lake)
* Dual Intel Xeon Gold 5218 processor (Cascade Lake)

### RAM
{: #cr_addingclusters-edge-cluster-ram}

You can select different values between 64 GB and 1.5 TB.

### Number of bare metal servers
{: #cr_addingclusters-edge-cluster-bare-metal}

The number of servers is set to two and cannot be changed. Both servers have the same configuration.

### Hostname prefix
{: #cr_addingclusters-edge-host-name-prefix}

The hostname prefix applies to all clusters in the instance. It must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 10 characters.

### Network diagram
{: #cr_addingclusters-edge-network-diagram}

You can customize the hostnames prefix individually by selecting **Configure hostnames individually**. It must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* No consecutive dash characters are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.

### Uplink speed
{: #cr_addingclusters-edge-uplink-speed}

The uplink speed of 10 Gb, which is selected by default.

### Networking type
{: #cr_addingclusters-edge-cluster-private-nics}

Select either **Public and private network** or **Private network only** for the gateway cluster.

## Summary
{: #cr_addingclusters-order-summary}

Based on your selected configuration for the cluster, the estimated price is instantly generated and displayed in the **Summary** pane. Click **Pricing details** to generate a PDF document with the price summary for the {{site.data.keyword.vmwaresolutions_short}} resources.

You can also add the provisioned resources to the {{site.data.keyword.cloud_notm}} estimate tool, by clicking **Add to estimate**. The estimate tool is useful if you want to get an approximate price of the selected {{site.data.keyword.vmwaresolutions_short}} resources together with other {{site.data.keyword.cloud_notm}} resources that you might consider to purchase.

## Procedure to add clusters to Cyber Recovery instances
{: #cr_addingclusters-procedure}

1. From the VMware Solutions console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery** table, click the instance that you want to add clusters to.

   Ensure that the instance status is **Available**. Otherwise, you cannot add clusters to the instance.
   {: important}

3. Click the **Infrastructure** tab and click **Create** on the upper right of the **Clusters** table.
4. On the **Create cluster** page, select the cluster type.
5. For workload clusters, enter the cluster name and complete the following configuration.
   1. Complete the licensing settings.
      * For Business Partner users, the vSphere license (Enterprise Plus edition) is included and purchased on your behalf.
      * For users who are not Business Partners, select **Include with purchase** for the new vSphere license to be purchased on your behalf. 
      * Bring Your Own License (BYOL) is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide** or **Use existing license** and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.
      * The **Use existing license** option is available only if you are using a BYOL vSphere or vSAN license for your instance. When the option is enabled, you can select the existing license only if the instance has enough capacity for the additional hosts.

   2. Complete the bare metal server configuration. 
      * If you want to host the cluster in a different {{site.data.keyword.cloud_notm}} data center than the one that the instance is hosted in, check the **Select a different location** box and choose the {{site.data.keyword.cloud_notm}} data center to host the instance.
      * For **Cascade Lake** CPU generation type, select the **CPU model**, the amount of **RAM**, and the **Number of bare metal servers**.
      * For **SAP-certified** NetWeaver, select one of the preset configurations. For **SAP-certified** HANA, select the **CPU model** and **RAM**.

   3. Complete the storage configuration.
      * If you select **NFS storage** and want to add and configure the same settings to all file shares, specify the **Number of shares**, **Size (GB)**, and **Performance**.
      * If you select **NFS storage** and want to add and configure file shares individually, select the **Configure shares individually** checkbox, then  click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share. You must select at least one file share.
      * If you select **vSAN storage**, specify the following values:
         * Size for the vSAN capacity disks
         * Number of vSAN capacity disks
         * Size for vSAN cache disks
         * Number of vSAN cache disks
         * vSAN license edition

      If you want more storage, check the **High performance with Intel Optane** box.

      By default, the **Enable vSAN deduplication and compression** box is selected. If you do not want to enable vSAN deduplication and compression, clear the checkbox.

6. For gateway clusters, complete the following configuration.
   1. For data center location, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") and select the geography, data center, and pod to host the cluster.
   2. Specify the cluster name.
   3. Select the CPU model, RAM size, and the number of bare metal servers.

7. For network interface settings, enter the hostname prefix, and then select the uplink speed and network type.

8. On the **Summary** pane, verify the cluster configuration before you add the cluster.
   1. Review the settings for the cluster.
   2. Review the estimated price of the cluster. Click **Pricing details** to generate a PDF summary. To save or print your order summary, click **Print** or **Download** on the upper right of the PDF window.
   3. Click the link or links of the terms that apply to your order, and confirm that you agree with these terms before you add the cluster.
   4. Click **Create**.

## Results after you add clusters to Cyber Recovery instances
{: #cr_addingclusters-results}

1. The deployment of the cluster starts automatically and the status of the cluster is changed to **Initializing**. You can check the status of the deployment by viewing the deployment history from the **Summary** page of the instance.
2. When the cluster is ready to use, its status changes to **Available**. The newly added cluster is enabled with vSphere High Availability (HA) and vSphere Distributed Resource Scheduler (DRS).

You cannot change the cluster name. Changing the cluster name might cause the add or remove ESXi servers operations in the cluster to fail.
{: important}

## Related links
{: #cr_addingclusters-related}

* [Expanding and contracting capacity for Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingservers)