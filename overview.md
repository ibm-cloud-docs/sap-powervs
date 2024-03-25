---

copyright:
  years: 2024
lastupdated: "2024-01-30"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Overview of {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture
{: #automation-solution-overview}

This automated deployable architecture guide is an extension to the main [IBM Cloud for SAP portfolio documentation](https://cloud.ibm.com/docs/sap), focusing on the automated reference architecture and steps required for the automated deployment.
{: shortdesc}

SAP solution provisioning on PowerVS using deployable architectures provides an automated deployment method to create a PowerVS landscape with SAP HANA systems. Comparing the provisioning via webUI, user interaction is minimized and SAP system deployment time is reduced from weeks to days.

Automated SAP provisioning on PowerVS described in this guide is based upon IBM Catalog deployable architectures. In this documentation we describe only specifics related to SAP HANA solution provisioning using deployable architectures.

## SAP on Power related deployable architectures
{: #automation-solution-components}

SAP solution provisioning as deployable architectures is a composition of two terraform based solutions
- [Power Virtual Server with VPC landing zone](/docs/powervs-vpc)
- This deployable architecture, Power Virtual Server for SAP HANA
