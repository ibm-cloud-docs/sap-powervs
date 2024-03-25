---

copyright:
  years: 2024
lastupdated: "2024-01-30"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Deployment dependencies
{: #automation-dependencies}

The SAP solution for end-to-end deployment by using deployable architectures is logically separated into the following steps:

1. Deploying Power Virtual Server with VPC landing zone. This deployed infrastructure hosts a management landscape on VPC for SAP solutions that are deployed as next. The provisioned IBM PowerVS workspace is connected to the VPC landing zone deployable architecture. Only one IBM PowerVS workspace might exist for each IBM PowerVS zone (data center) in one IBM Cloud account. You can connect multiple PowerVS workspaces to the same VPC landing zone if the private CIDR network ranges of each IBM PowerVS infrastructure do not overlap. In that case, the PowerVS workspaces are connected to the same VPC landing zone and to each other.

You must have an existing deployment of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. This can be deployed from IBM catalog tile. Instructions are provided (here)[docs/powervs-vpc?topic=powervs-vpc-powervs-automation-overview].

If you already have a PowerVS workspace, then you can use the [Import PowerVS workspace](/docs/powervs-vpc?topic=powervs-vpc-powervs-automation-overview#overview-powervs-workspace-import-variant) variation of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture instead of deploying a new {{site.data.keyword.powerSysFull}} with VPC landing zone deployable architecture.  The 'import-workspace' solution creates a schematics workspace by taking pre-existing VPC and PowerVS infrastructure resource details as inputs. The ID of this schematics workspace will be the pre-requisite workspace id required by 'Power Virtual Server for SAP HANA' to create and configure the PowerVS instances for SAP on top of the existing infrastructure. 

Check the **pre-requisites** for this variation [here](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-infrastructure/tree/main/solutions/import-workspace#pre-requisites).


2. Deploying Power Virtual Server for SAP HANA on top of Power Virtual Server with VPC landing zone. You can deploy multiple SAP solutions (systems) in one IBM PowerVS workspace that uses this deployable architecture if the private CIDR network range of each SAP solution does not overlap.

    The second step relies on the previous one. For instance, if you deploy Power Virtual Server for SAP HANA, you enter the IBM Schematics workspace ID of the Power Virtual Server with VPC landing zone. The prerequisite dependency is constrained by type. This dependency means that not every PowerVS workspace is accepted for the Power Virtual Server for SAP HANA deployable architecture, but only the one created by the Power Virtual Server with VPC landing zone.
    {: note}

Certain steps are combined together and provided as one deployment step to simplify provisioning. For example, the Power Virtual Server with VPC landing zone offers a full-stack variation that deploys both the VPC landing zone and the PowerVS workspace in one step. In addition, you can deploy the Power Virtual Server with VPC landing zone as an extension that will create an additional PowerVS workspace and connect it with an existing VPC landing zone.
