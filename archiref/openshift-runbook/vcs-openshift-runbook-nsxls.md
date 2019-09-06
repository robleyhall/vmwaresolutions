---

copyright:

  years:  2019

lastupdated: "2019-09-04"

subcollection: vmware-solutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# OpenShift NSX logical switches configuration
{: #openshift-runbook-runbook-nsxls-intro}

This section details the NSX logical switches that are utilized to support the OpenShift 4.1 environment. To use this information, you must understand how to create these components and add the configuration.

Review [Add a logical switch](https://docs.vmware.com/en/VMware-NSX-Data-Center-for-vSphere/6.4/com.vmware.nsx.admin.doc/GUID-295720D5-DD75-4523-9095-1D694D99717A.html){:external}. PowerNSX commands are provided if you would want to use this method.

## NSX Logical Switches
{: #openshift-runbook-runbook-nsxls-config}

The design requires two NSX Logical Switches:

* Transit - This logical switch is used to connect the DLR and the ESGs. The DLR Control VMs will have an interface on this network.
* OpenShift - This logical switch is used for the OpenShift VM network. The DLR has a connection to this logical switch.
* HA - This logical switch is used for the DLR Control VMs. There is no need to assign an IP range to this network as NSX will assign internal IP range to it.

## PowerNSX commands
{: #openshift-runbook-runbook-nsxls-powernsx}

This section provides example PowerNSX commands to script the provisioning and configuration of the NSX logical switches. Use the following table to document the parameters you will need for your deployment, examples are shown that match the deployment described previously.

| Parameters | Example | Your Deployment |
| --- | --- | --- |
| vCenter Server IP address | | |
| vCenter User | | |
| vCenter Password | | |
| NSX Transport Zone| transport-1 | |

{: caption="Table 1. PowerNSX LS Parameters" caption-side="top"}

```powernsx
# Connect to NSX Manager
Connect-NsxServer -vCenterServer <IP_Address> -User <UserName> -Password '<Password>'

# Create Logical switches
Get-NsxTransportZone transport-1 | new-nsxlogicalswitch -Name OpenShift-LS -Description "OpenShift network"
Get-NsxTransportZone transport-1 | new-nsxlogicalswitch -Name OpenShift-Transit -Description "OpenShift transit network"
Get-NsxTransportZone transport-1 | new-nsxlogicalswitch -Name OpenShift-HA -Description "OpenShift DLR HA network"

# Disconnect
Disconnect-NsxServer
```

## Related links
{: #openshift-runbook-runbook-nsxdls-related}

* [OpenShift Bastion host setup](/docs/services/vmwaresolutions?topic=vmware-solutions-openshift-runbook-runbook-bastion-intro)
* [Red Hat OpenShift 4.1 user provider infrastructure installation](/docs/services/vmwaresolutions?topic=vmware-solutions-openshift-runbook-runbook-install-intro)