---

copyright:

  years:  2016, 2023

lastupdated: "2023-02-09"

keywords: vSphere scale cluster, scale vSphere, external vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Scaling clusters created outside of the console
{: #vs_orderingforclustersoutside}

You can use the VMware vSphere® offering to scale existing vSphere clusters that are created outside of the {{site.data.keyword.vmwaresolutions_full}} console. To scale a vSphere cluster that is created outside of the console, re-create the cluster with the same settings with the console and then scale the cluster.

## Requirements for VMware vSphere
{: #vs_orderingforclustersoutside-req}

Ensure that you complete the following tasks:
* If you are ordering a vSphere cluster for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
* Review the requirements and considerations in [Planning for VMware vSphere](/docs/vmwaresolutions?topic=vmwaresolutions-vs_planning).

## Procedure to scale clusters created outside of the console
{: #vs_orderingforclustersoutside-procedure}

1. In the VMware Solutions console, click the **VMware vSphere** card in the **Platforms** section.
2. On the **Create** tab, select **Create new** and ensure that **New cluster** is displayed in the **Cluster configurations** list.
3. Create a cluster with the same settings as the existing cluster that is created outside of the {{site.data.keyword.vmwaresolutions_short}} console. For more information, see [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req).  
   Under **Network interface**, you must choose the option to select existing VLANs.
   {: note}

4. In the **Summary** pane, verify the cluster configuration, and then click **Save configuration**.
5. Back on the **VMware Solutions** page, ensure that the **VMware vSphere** card is selected.
6. Click the **Scale existing** tab. From the **Cluster configurations** list, select the cluster that you recently created.
7. In the **Bare metal server** section, specify the number of {{site.data.keyword.cloud_notm}} bare metal servers that you want to add to the cluster.
8. If the cluster does not include the FortiGate® 300 Series Security Appliance HA Pair on its public VLAN, you can order one by selecting **Include with purchase** under **FortiGate Physical Appliance 300 Series HA Pair**.
9. In the **Summary** pane, verify the ordered configuration and the estimated price, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Results
{: #vs_orderingforclustersoutside-results}

The deployment of the cluster starts automatically, and you receive an email confirmation that the order is being processed. When the cluster is ready to use, you are notified by email.

The vSphere clusters, unlike the VMware vCenter Server® instances, are not displayed on the **Resources** pages. The vSphere cluster servers are listed under **Devices** on the [Classic Infrastructure](https://cloud.ibm.com/classic) page.
{: note}

## Related links
{: #vs_orderingforclustersoutside-related}

* [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req)
* [Ordering vSphere clusters based on existing configurations](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingbasedonexistingconfig)
* [Scaling existing vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_scalingexistingclusters)
