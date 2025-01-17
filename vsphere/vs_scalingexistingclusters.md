---

copyright:

  years:  2016, 2023

lastupdated: "2023-02-09"

keywords: vSphere scale cluster, scale vSphere, scale vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Scaling existing vSphere clusters
{: #vs_scalingexistingclusters}

You can scale out a VMware vSphere® cluster that you ordered or saved in the {{site.data.keyword.vmwaresolutions_full}} console. To do so, add VMware ESXi™ servers or order a FortiGate® 300 Series Security Appliance HA pair for the cluster.

## Requirements for VMware vSphere
{: #vs_scalingexistingclusters-req}

Ensure that you complete the following tasks:
* If you are ordering a vSphere cluster for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
*  Review the requirements and considerations in [Planning for vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_planning).
*  Verify that you received an email with the confirmation that the cluster you want to scale is ready to use.

## Procedure to scale existing clusters
{: #vs_scalingexistingclusters-procedure}
{: help}
{: support}

1. In the VMware Solutions console, click the **VMware vSphere** card in the **Platforms** section.
2. On the **Create** tab, select **Scale existing** and select the cluster that you want to scale from the **Cluster configurations** list.
3. Review the cluster settings that are automatically completed, update the settings according to your needs, and complete any required fields. In this step, when you scale out a configuration, the **Number of bare metal servers** field refers to the number of servers to add to the configuration. It doesn't refer to the total number of servers in the configuration after the scale operation. For more information about the settings, see [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req).
4. If the cluster does not include the FortiGate 300 Series Security Appliance HA Pair on its public VLAN, you can order the appliance. To do so, select the **Include with purchase** checkbox under **FortiGate Physical Appliance 300 Series HA Pair**.
5. In the **Summary** pane, verify the ordered configuration and the estimated price.
   * To save the configuration as a template without placing an order, click **Save configuration**.
   * To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

### Results
{: #vs_scalingexistingclusters-results}

The cluster scaling starts automatically. You receive an email confirmation that the order is being processed. When the cluster is ready to use, you are notified by email. If the cluster that you are scaling is not ready to use, you might receive an error message.

The vSphere clusters, unlike the VMware vCenter Server® instances, are not displayed on the **Resources** pages. The vSphere cluster servers are listed under **Devices** on the [Classic Infrastructure](https://cloud.ibm.com/classic) page.
{: note}

## Related links
{: #vs_scalingexistingclusters-related}

* [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req)
* [Ordering vSphere clusters based on existing configurations](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingbasedonexistingconfig)
* [Scaling clusters created outside of the console](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingforclustersoutside)
