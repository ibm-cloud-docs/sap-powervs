---

copyright:
  years: 2024
lastupdated: "2024-05-27"

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

## SAP ready PowerVS Variation
{: #overview-sap-ready-powervs}

'SAP ready PowerVS' variation of 'Power Virtual Server for SAP HANA' creates a basic and expandable SAP system landscape builds on the foundation of the [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. PowerVS instances for SAP HANA, SAP NetWeaver and optionally for shared SAP files are deployed and preconfigured for SAP installation.

Services such as DNS, NTP and NFS running in VPC and provided by 'Power Virtual Server with VPC landing zone' are leveraged.
Transit gateway provide the network bridge between the IBM Power infrastructure and the IBM VPC and public internet. 
The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management and the network connectivity configuration provided by 'Power Virtual Server with VPC landing zone'.

## SAP S/4HANA or BW/4HANA Variation
{: #overview-sap-s4hana-bw4hana}

SAP S/4HANA or BW/4HANA' variation of 'Power Virtual Server for SAP HANA' creates a basic and expandable SAP system landscape builds on the foundation of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. PowerVS instances for SAP HANA, SAP NetWeaver and optionally for shared SAP files are deployed and preconfigured for SAP installation. 

**S/4HANA or BW/4HANA solution is installed based on selected version.**
Services such as DNS, NTP and NFS running in VPC and provided by 'Power Virtual Server with VPC landing zone' are leveraged.

Transit gateway provide the network bridge between the IBM Power infrastructure and the IBM VPC and public internet. 
The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management and the network connectivity configuration provided by 'Power Virtual Server with VPC landing zone'.
