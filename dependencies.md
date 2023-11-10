---

copyright:
  years: 2023
lastupdated: "2023-07-10"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Deployment dependencies
{: #sap-power-automation-dependencies}

The SAP solution end-to-end deployment by using deployable architectures is logically separated into the following steps:

1. Deploying Power Virtual Server with VPC landing zone. This deployed infrastructure hosts management landscape on VPC for SAP solutions that are deployed as next. Provisioned IBM PowerVS workspace is connected to VPC landing zone. There might exist only one IBM PowerVS workspace per IBM PowerVS zone (data center) in one IBM Cloud account. Multiple PowerVS workspaces might be connected to the same VPC landing zone if the private CIDR network ranges of each IBM PowerVS infrastructure do not overlap. Multiple PowerVS workspaces in that case are connected to the same VPC landing zone and to each other. 
2. Deploying Power Virtual Server for SAP HANA on top of Power Virtual Server with VPC landing zone. Multiple SAP solutions (systems) might be deployed within one IBM PowerVS workspace that uses this deployable architecture if the private CIDR network range of each SAP solution does not overlap.

The second step relies on the previous one. For instance, if you deploy Power Virtual Server for SAP HANA, you enter IBM Schematics workspace ID of the Power Virtual Server with VPC landing zone. The prerequisite dependency is constrained by type. Means, for Power Virtual Server for SAP HANA deployable architecture not every PowerVS workspace is accepted, but only the one created by Power Virtual Server with VPC landing zone.
{: note}

Certain steps are combined together and provided as one deployment step to simplify provisioning. For instances, the Power Virtual Server with VPC landing zone offers a full-stack variation that deploys both VPC landing zone and PowerVS workspace in one step. In addition, you might deploy the Power Virtual Server with VPC landing zone as an extension that will create an additional PowerVS workspace and connect it with an existing VPC landing zone.
