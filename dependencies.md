---

copyright:
  years: 2023
lastupdated: "2023-11-13"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Deployment dependencies
{: #sap-power-automation-dependencies}

The SAP solution for end-to-end deployment by using deployable architectures is logically separated into the following steps:

1. Deploying Power Virtual Server with VPC landing zone. This deployed infrastructure hosts a management landscape on VPC for SAP solutions that are deployed as next. The provisioned IBM PowerVS workspace is connected to the VPC landing zone deployable architecture. Only one IBM PowerVS workspace might exist for each IBM PowerVS zone (data center) in one IBM Cloud account. You can connect multiple PowerVS workspaces to the same VPC landing zone if the private CIDR network ranges of each IBM PowerVS infrastructure do not overlap. In that case, the PowerVS workspaces are connected to the same VPC landing zone and to each other.
2. Deploying Power Virtual Server for SAP HANA on top of Power Virtual Server with VPC landing zone. You can deploy multiple SAP solutions (systems) in one IBM PowerVS workspace that uses this deployable architecture if the private CIDR network range of each SAP solution does not overlap.

    The second step relies on the previous one. For instance, if you deploy Power Virtual Server for SAP HANA, you enter the IBM Schematics workspace ID of the Power Virtual Server with VPC landing zone. The prerequisite dependency is constrained by type. This dependency means that not every PowerVS workspace is accepted for the Power Virtual Server for SAP HANA deployable architecture, but only the one created by the Power Virtual Server with VPC landing zone.
    {: note}

Certain steps are combined together and provided as one deployment step to simplify provisioning. For example, the Power Virtual Server with VPC landing zone offers a full-stack variation that deploys both the VPC landing zone and the PowerVS workspace in one step. In addition, you can deploy the Power Virtual Server with VPC landing zone as an extension that will create an additional PowerVS workspace and connect it with an existing VPC landing zone.
