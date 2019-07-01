---

copyright:

  years:  2016, 2019

lastupdated: "2019-06-28"

keywords: single-node trial, data protection DR, tech specs data protection DR

subcollection: vmware-solutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Single-node Trial for Data Protection and Disaster Recovery overview
{: #dr_backup_bundle_overview}

The Single-node Trial for Data Protection and Disaster Recovery allows you to test drive
 {{site.data.keyword.cloud}} to migrate and recover VMware workloads to the {{site.data.keyword.cloud_notm}}. In addition, Single-node Trial for Data Protection and Disaster Recovery includes the Veeam on {{site.data.keyword.cloud_notm}}, VMware HCX on {{site.data.keyword.cloud_notm}}, and Zerto on {{site.data.keyword.cloud_notm}} services.

The Single-node Trial is a trial version of VMware vCenter Server on {{site.data.keyword.cloud_notm}} that provides the single-tenant VMware platform that can be managed using the same tools as in on-premises environments. You can take advantage of the speed and scale of the cloud while maintaining the same level of control and visibility that is provided on-premises.

The trial is designed for migration of up to 20 simple development or test workloads using vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle. Automation will install and configure VMware HCX in the {{site.data.keyword.cloud_notm}}, provide an on-premises HCX activation key, and install Veeam on {{site.data.keyword.cloud_notm}} and Zerto on {{site.data.keyword.cloud_notm}} in a matter of hours. You can back up and replicate 20 virtual machines (VMs) with Veeam on {{site.data.keyword.cloud_notm}} and Zerto on {{site.data.keyword.cloud_notm}}. 

The Single-node Trial for Data Protection and Disaster Recovery is for proof of concept (POC) only. Do not run production workloads on this environment. Management functions such as adding and removing hosts and clusters, ordering additional add-on services, and applying updates are not supported.
{:important}

After your Single-node Trial instance is deployed, you can use [IBM On Demand Consulting for Hybrid Cloud](https://public.dhe.ibm.com/software/data/sw-library/services/ODC.pdf){:external} from [IBM Analytics Cloud Expert Services](https://www.ibm.com/analytics/us/en/services/cloud-expert-services.html){:external} for assistance with your instance. Additionally, [{{site.data.keyword.cloud_notm}} Garage Services](https://www.ibm.com/cloud/garage/){:external} can help you accelerate application modernization through the latest cloud native practices.

This trial is intended for use up to 90 days. Monthly recurring charges are billed based on your billing schedule, not when the instance is ordered. If the instance is not cancelled on or before the last day of your billing cycle, you are charged for the next month. Most likely a 90 day trial result in four months of charges, unless the cancellation is completed before the forth month begins.
{:note}

When you are finished with the trial, you can delete this environment and provision a new environment that meets your capacity needs.

## Technical specifications for Single-node Trial for Data Protection and Disaster Recovery instances
{: #dr_backup_bundle_overview-tech-specs}

The following components are included in your Single-node Trial for Data Protection and Disaster Recovery instance.

The availability and pricing of standardized hardware configurations might vary based on the {{site.data.keyword.CloudDataCent_notm}} that is selected for deployment.
{:note}

### Bare Metal Server
{: #dr_backup_bundle_overview-bare-metal}

Skylake Dual Intel Xeon Gold 5120 Processor / 28 cores total, 2.2 GHz with 384 GB RAM for up to about 20 VMs

#### CPU over-commits
{: #dr_backup_bundle_overview-cpu}

16:1 CPU over-commit for vCenter Server management, HCX, and 20 customer workload VMs

#### RAM over-commits
{: #dr_backup_bundle_overview-ram}

* 1.22:1 RAM over-commit for a customer deployment of 20 workload VMs with 8 GB each
* 1:1 (no over-commit) for a customer deployment of nine workload VMs with 8 GB each

### NFS storage
{: #dr_backup_bundle_overview-nfs-storage}

* 2 TB for management
* 1 TB for customer workload (for 20 customer VMs)

### Networking specifications for Single-node Trial for Data Protection and Disaster Recovery instances
{: #dr_backup_bundle_overview-networking-specs}

The following networking components are ordered:
*  10 Gbps dual public and private network uplinks
*  Three VLANs (Virtual LANs): one public VLAN and two private VLANs
*  One VXLAN (Virtual eXtensible LAN) with DLR (Distributed Logical Router) for potential east-west communication between local workloads that are connected to layer 2 (L2) networks. The VXLAN is deployed as a sample routing topology, which you can modify, build on it, or remove it. You can also add security zones by attaching more VXLANs to new logical interfaces on the DLR.
*  Two VMware NSX Edge Services Gateways:
  * A secure management services VMware NSX Edge Services Gateway (ESG) for outbound HTTPS management traffic, which is deployed by IBM as part of the management networking typology. This ESG is used by the IBM management VMs to communicate with specific external IBM management components that are related to automation.

    This ESG is not accessible to you and you cannot use it. If you modify it, you might not be able to manage the Single-node Trial for Data Protection and Disaster Recovery instance from the {{site.data.keyword.vmwaresolutions_short}} console. In addition, note that using a firewall or disabling the ESG communications to the external IBM management components will cause {{site.data.keyword.vmwaresolutions_short}} to become unusable.
    {:important}
  * A secure customer-managed VMware NSX Edge Services Gateway for outbound and inbound HTTPS workload traffic, which is deployed by IBM as a template that can be modified by you to provide VPN access or public access.

### Virtual Server Instances
{: #dr_backup_bundle_overview-vsi}

The following virtual server instances (VSIs) are ordered:

* A VSI for IBM CloudBuilder, which is cancelled after the instance deployment is completed.
* A Microsoft Windows Server VSI for Microsoft Active Directory (AD) is deployed and can be looked up. The VSI functions as the DNS for the instance where the hosts and VMs are registered.
* A VSI for Zerto on {{site.data.keyword.cloud_notm}} - Zerto Virtual Manager.
* A VSI with Veeam Backup and Replication 9.5 OS Add-on and Veeam Availability Suite 9.5.

### IBM-provided licenses and fees
{: #dr_backup_bundle_overview-license-and-fee}

The following licenses are included with your Single-node Trial for Data Protection and Disaster Recovery instance order.

* The vCenter Server with Hybridity Bundle licenses:
  * VMware vSphere Enterprise Plus 6.7u1
  * VMware vCenter Server 6.5
  * VMware NSX Service Providers Advanced Edition 6.4
* {{site.data.keyword.cloud_notm}} Automation Manager 3.1.2

Single-node Trial for Data Protection and Disaster Recovery instances do not support Bring Your Own License.
{:note}

## Technical specifications for VMware HCX on IBM Cloud
{: #dr_backup_bundle_overview-hcx-tech-specs}

The Single-node Trial for Data Protection and Disaster Recovery includes HCX on {{site.data.keyword.cloud_notm}}. The following components are ordered and included in the HCX on {{site.data.keyword.cloud_notm}} service.

On-premises HCX instances include only licensing and activation.
{:note}

### An active/passive pair of VMware NSX Edge Services Gateways for HCX Management
{: #dr_backup_bundle_overview-esg}

* CPU: 6 vCPU
* RAM: 8 GB
* Disk: 3 GB VMDK

### HCX Management Appliance - Virtual Machine
{: #dr_backup_bundle_overview-hcx-mgmt-appliance}

* CPU: 4 vCPU
* RAM: 12 GB
* Disk: 60 GB VMDK

Additional HCX appliances are deployed during configuration as necessary for L2 connectivity, WAN optimization, and gateway connections.

### Networking specifications for HCX on IBM Cloud
{: #dr_backup_bundle_overview-hcx-networking-specs}

* One public portable subnet with 16 IP addresses
* Two private portable subnets with 64 IP addresses
* Eight IP addresses from private portable vMotion subnet

## Technical specifications for Veeam on {{site.data.keyword.cloud_notm}}
{: #dr_backup_bundle_overview-veeam-tech-specs}

The Single-node Trial for Data Protection and  Disaster Recovery includes Veeam on {{site.data.keyword.cloud_notm}}. The following components are ordered and included in the Veeam on {{site.data.keyword.cloud_notm}} service.

* 25 pack license of the Veeam Availability Suite
* 4000 GB storage
* 0.25 IOPS/GB storage performance
* Windows Server 2016 Standard Edition (64-bit)
* 4 x 2.0 GHz Cores
* 8 GB RAM
* 1 Gbps private network uplink
* 100 GB disk (SAN)

## Technical specifications for Zerto on {{site.data.keyword.cloud_notm}}
{: #dr_backup_bundle_overview-zerto-tech-specs}

The Single-node Trial for Data Protection and Disaster Recovery includes Zerto on {{site.data.keyword.cloud_notm}}. The following components are ordered and included in the Zerto on {{site.data.keyword.cloud_notm}} service.

* Zerto Virtual Replication V6.5u3 License
* One Virtual Service Instance (VSI) - Zerto Virtual Manager
* 2 x 2.0 GHz cores
* 4 GB RAM
* Windows Server 2016 Standard Edition (64-bit)
* 100 GB (SAN) disk

## Technical specifications for IBM Cloud Automation Manager
{: #dr_backup_bundle_overview-cam-tech-specs}

{{site.data.keyword.cloud_notm}} Automation Manager 3.1.2 is installed using the Development/Test topology on all Single-node Trial for Data Protection and Disaster Recovery instances. For more information about {{site.data.keyword.cloud_notm}} Automation Manager, see [{{site.data.keyword.cloud_notm}} Automation Manager documentation](https://www.ibm.com/support/knowledgecenter/en/SS2L37_3.1.2.0/kc_welcome.html){: external}.

## Related links
{: #dr_backup_bundle_overview-related}

* [VMware HCX resources](https://hcx.vmware.com/#/docs){:external}
* [VMware HCX User Guide](https://docs.vmware.com/en/VMware-HCX/services/user-guide/GUID-BFD7E194-CFE5-4259-B74B-991B26A51758.html){:external}
* [Managing Veeam on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions?topic=vmware-solutions-managingveeam)
* [Managing Zerto on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions?topic=vmware-solutions-managingzertodr)