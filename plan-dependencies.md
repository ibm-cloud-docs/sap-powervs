---

copyright:
  years: 2023, 2025
lastupdated: "2025-05-13"
subcollection: sap-powervs
keywords:

---

{{site.data.keyword.attribute-definition-list}}

# Deployment dependencies
{: #automation-dependencies}

The SAP solution for end-to-end deployment by using deployable architectures is logically separated into the following steps:

1. You must have an existing deployment of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. This can be deployed from IBM catalog tile. Instructions are provided [here](/docs/powervs-vpc?topic=powervs-vpc-automation-solution-overview).

Only following variations are supported to proceed with the deployment of SAP Ready PowerVS and SAP S/4HANA or BW/4HANA.

- Create a new architecture: [Standard Landscape Variation](/docs/powervs-vpc?topic=powervs-vpc-deploy-arch-ibm-pvs-inf-standard)
- Extend {{site.data.keyword.powerSysFull}} with VPC landing zone: [Extend Standard Landscape Variation](/docs/powervs-vpc?topic=powervs-vpc-deploy-arch-ibm-pvs-inf-extension)

1. Deploying {{site.data.keyword.powerSysFull}} for SAP HANA on top of {{site.data.keyword.powerSysFull}} with VPC landing zone. You can deploy multiple SAP solutions (systems) in one IBM PowerVS workspace that uses this deployable architecture if the private CIDR network range of each SAP solution does not overlap.

    The second step relies on the previous one. For instance, if you deploy {{site.data.keyword.powerSysFull}} for SAP HANA, you enter the IBM Schematics workspace ID of the {{site.data.keyword.powerSysFull}} with VPC landing zone. The prerequisite dependency is constrained by type. This dependency means that not every PowerVS workspace is accepted for the {{site.data.keyword.powerSysFull}} for SAP HANA deployable architecture, but only the one created by the {{site.data.keyword.powerSysFull}} with VPC landing zone.
    {: note}
