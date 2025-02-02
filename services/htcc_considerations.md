---

copyright:

  years:  2016, 2020

lastupdated: "2020-10-13"

keywords: HyTrust CloudControl, HTCC, tech specs HTCC

subcollection: vmwaresolutions


---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# HyTrust CloudControl overview
{: #htcc_considerations}

The HyTrust® CloudControl™ service enforces and controls compliance against security standards, which includes role-based access control (RBAC), approval, and auditing. When the service is combined with HyTrust DataControl®, the service ensures that virtual machines and workload data don't leave a particular region, cluster, or VMware ESXi™ server within the {{site.data.keyword.cloud}} data center.
{: shortdesc}

The following versions of the HyTrust CloudControl service are installed, based on the VMware NSX® networking solution type of your instance:
* 5.6 for vCenter Server with NSX-V
* 6.2 for vCenter Server with NSX-T

{{site.data.keyword.vmwaresolutions_full}} offers promotions for some add-on services. Promotional pricing offers a number of months free of charge for a service’s licenses, if the service has license charges. For more information, see [Promotions for VMware Solutions add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingremovingservices#vc_addingremovingservices-service-promotions).

## Technical specifications for HyTrust CloudControl
{: #htcc_considerations-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingremovingservices#vc_addingremovingservices-resource-requirements).

For VMware vCenter Server® with NSX-T instances, HyTrust CloudControl v6.2 is pre-configured with connections to the following components:
* Microsoft® Active Directory™
* vCenter Server
* VMware NSX-T

Sample users and groups are pre-configured in Active Directory (AD) and are displayed on the service details page. If you delete HyTrust CloudControl, the sample users are deleted from AD too. A sample trust manifest is set up that gives single sign-on (SSO) permissions to the sample users that are created. You can change this setting or customize it for your own requirements.

During the pre-configuration of HyTrust CloudControl, global PIP is enabled.

The following components are ordered and included in the HyTrust CloudControl service:

### HyTrust CloudControl appliance
{: #htcc_considerations-appliance}

* CPU: 4 vCPU
* RAM: 16 GB
* Disk:
  * For version 5.6: 70 GB VMDK resident on vSAN
  * For version 6.2: 186 GB VMDK resident on vSAN
* Network: Placed on VLAN-backed private portable network specified for management

### High availability
{: #htcc_considerations-ha}

Two CloudControl appliances are deployed in an active-passive configuration.

### Licenses and fees
{: #htcc_considerations-licenses}

Per-host license: A HyTrust CloudControl license is ordered for each host in the environment.

## Considerations when you delete HyTrust CloudControl
{: #htcc_considerations-remove}

Before you delete the HyTrust CloudControl service, ensure that you disable **Root Password Vaulting**, if configured, and that you delete all protected hosts from HyTrust CloudControl.

## Related links
{: #htcc_considerations-related}

* [Ordering HyTrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-htcc_ordering)
* [Managing HyTrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-managinghtcc)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [HyTrust website](https://www.hytrust.com/){:external}
