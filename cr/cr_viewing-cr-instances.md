---

copyright:

  years:  2022, 2023

lastupdated: "2023-04-03"

keywords: view Cyber Recovery, view instance, view instance details, instance view Cyber Recovery

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Viewing Cyber Recovery instances
{: #cr_viewinginstances}

View the summary and detailed information of the Cyber Recovery instances that are provisioned for different user accounts.

## Procedure to view summary for Cyber Recovery instances
{: #cr_viewinginstances-procedure-view-inst-summary}

To view a summary of all the Cyber Recovery instances that are provisioned for a user account, complete the following steps:

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. From the console banner, click the **Avatar** icon ![Avatar icon](../../icons/i-avatar-icon.svg "Avatar"), and then click the **Account** field. Select the user account that you want to check instances for.
3. In the **Cyber Recovery** table, view the list of instances that are provisioned in the selected user account.

| Item | Description |
|:---- |:----------- |
| Name | The name of the instance. |
| Type | The type of Cyber Recovery instance. Instance type is **Single-zone**. |
| Version | The release version that the instance was deployed in, or upgraded to. |
| Location | The {{site.data.keyword.cloud_notm}} data center where the instance is hosted. |
| Creation time | The date and time when the instance was created. |
| Status | The status of the instance. |
{: caption="Table 1. Cyber Recovery instance items" caption-side="bottom"}

The instance can have different statuses.

| Status | Description |
|:------ |:----------- |
| Creating | The instance is being created. |
| Building | The instance is being configured. |
| Available | The instance is ready to use. |
| Modifying | The instance is being modified. |
| Failed | The creation, configuration, or modification process failed. |
| Deleting | The instance is being deleted. |
| Deletion error | An error occurred when the instance was being deleted. |
| Deleted | The instance is deleted. |
{: caption="Table 2. Cyber Recovery instances status descriptions" caption-side="bottom"}

## Procedure to view the property details for Cyber Recovery instances
{: #cr_viewinginstances-procedure-view-inst-property}

To view the property details of an instance, complete the following steps.

1. In the **Cyber Recovery** table, click an instance name.
2. Under **Properties**, view the details for the instance.

| Property | Description |
|:-------- |:----------- |
| Name | The name of the instance. |
| ID | The ID of the instance. |
| Location | The {{site.data.keyword.cloud_notm}} data center where the instance is hosted. |
| Current version | The current version of {{site.data.keyword.vmwaresolutions_short}}. |
| Cyber Recovery version | The Cyber Recovery version. \n \n **Note:** The Cyber Recovery versions that are displayed on the {{site.data.keyword.vmwaresolutions_short}} console and the VMware vSphere® Web Client are slightly different. Both are correct. |
| VMware NSX® networking solution | NSX-T™ |
| VMware vSphere version[^vsphere] | The version of VMware vSphere. |
| NSX for vSphere | The VMware NSX for vSphere product version. |
| _VMware component_ license | If you selected to use your own VMware® license for any of the VMware components on the **Licensing** page when you ordered the instance, the VMware component name and the license key that you entered for the component are displayed. \n \n Examples of VMware component licenses can include **NSX license**, **Cyber Recovery license**, and **vSAN license**. |
| NSX license edition | The version and edition of the VMware NSX license. |
| Root domain | The root domain name is the DNS domain name and the Microsoft® Active Directory™ (AD) forest root name. |
| SSO domain | The SSO domain is the vSphere single sign-on domain. The SSO domain name is fixed for all deployed Cyber Recovery instances with a value of **`vsphere.local`**. |
| Subdomain[^subdomain] | The subdomain is the DNS subdomain name of the root domain name where the local Cyber Recovery instance hostnames are located. The subdomain name is in the format `cyber recovery_instance_name.root.domain_name`. |
{: caption="Table 3. Cyber Recovery instance properties" caption-side="bottom"}

[^subdomain]: The subdomain label is not used for VMware vSphere 7 instances.

## Procedure to view access information for Cyber Recovery instances
{: #cr_viewinginstances-procedure-view-access-info}

Under **Access information**, view the access information for the instance-related components. The passwords that are displayed are initial passwords that are generated by the system. If you change them outside of the {{site.data.keyword.vmwaresolutions_short}} console, they are not updated on the instance summary page.

| Component | Description |
|:--------- |:----------- |
| AD/DNS IP or IPs | The two IP addresses for the two AD servers. |
| AD/DNS FQDN | The AD/DNS server fully qualified domain names (FQDN); two FQDNs for the two AD servers. \n \n **Note:** The same administrator password can be used to connect to all the AD/DNS servers by using a remote desktop connection. |
| Cyber Recovery/PSC IP | The IP address of the Cyber Recovery. |
| Cyber Recovery/PSC FQDN | The Cyber Recovery fully qualified domain name (FQDN). |
| Cyber Recovery/PSC ADMIN | The Cyber Recovery SSO username and password that you can use to log in to the Cyber Recovery by using the vSphere Web Client. |
| Cyber Recovery/PSC SSH | The username and password that you can use to access the Cyber Recovery VM through SSH connection. |
| NSX Manager IP | The IP address of the NSX Manager. |
| NSX Manager FQDN | The NSX Manager fully qualified domain name (FQDN). |
| NSX Manager HTTP | The username and password that is used to access the NSX Manager web console. |
| NSX Controllers IPs | The IP address or addresses for the NSX-T node VM. |
| NSX Controllers SSH | The username and password that you can use to access the NSX-T node VM through KVM or SSH connection. |
| Customer Edge VM IPs | The IP address or addresses for the Customer Edge VM. |
| Customer Edge VM SSH | The username and password that you can use to access the Customer Edge VM through KVM or SSH connection. |
| NSX Service Edge VM IPs | The IP address or addresses for the Service Edge VM. |
| NSX Service Edge VM SSH | The username and password that you can use to access the Service Edge VM through KVM or SSH connection. |
{: caption="Table 4. Cyber Recovery access information for instance-related components" caption-side="bottom"}

## Procedure to view deployment history for Cyber Recovery instances
{: #cr_viewinginstances-procedure-view-deploy-history}

Click **Deployment history** from the left navigation pane to view the deployment history for the instance.

| Item | Description |
|:---- |:----------- |
| Date | The date and time when the instance status is changed. |
| Summary | The details of the change. |
{: caption="Table 5. Cyber Recovery instance deployment history" caption-side="bottom"}

## What to do if errors occur
{: #cr_viewinginstances-if-errors-occur}

If errors occur during instance deployment or instance deletion, the {{site.data.keyword.cloud_notm}} Support team is automatically notified. To inquire about the status of your ticket, follow the steps in [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

## What to do next
{: #cr_viewinginstances-next}

Manage your instances from the VMware Solutions console or the VMware vSphere Web Client.

You must log in to the VPN portal of the {{site.data.keyword.cloud_notm}} data center before you click **vCenter console** on the instance summary page to start managing your VMware ESXi™ servers from the vSphere Web Client. Hover over **vCenter console** and follow the instructions to ensure that you meet all requirements and you completed the necessary steps before you access the vSphere Web Client.
{: important}

Review the following topics for information to help you complete the login instructions:
*  For the requirements and necessary steps before you access the vSphere Web Client, see [Timeout reached while connecting to the vSphere Web Client](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_timeout_vc_console).
*  For a list of access points to log in to the {{site.data.keyword.cloud_notm}} infrastructure Private Network by using VPN, see [VPN access](https://www.ibm.com/cloud/vpn-access){: external}.
*  If you have problems when you deploy an OVF (Open Virtualization Format) file by using the vSphere Web Client, see [Deploying an OVF file using the vSphere Web Client](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_deploy_ovf).

## Related links
{: #cr_viewinginstances-related}

* [Procedure to order Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-order-procedure)
* [Adding clusters to Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingclusters)
* [Adding ESXi servers to Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingservers)
* [Deleting Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_deletinginstance)
