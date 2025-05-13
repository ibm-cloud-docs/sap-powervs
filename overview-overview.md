---

copyright:
  years: 2023, 2025
lastupdated: "2025-05-13"
subcollection: sap-powervs
keywords: powervs, landing zone, sap, automation, deployable architecture, hana, s4hana, bw4hana

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
-  [{{site.data.keyword.powerSysFull}} with VPC landing zone](/docs/powervs-vpc)
-  This deployable architecture, {{site.data.keyword.powerSysFull}} for SAP HANA

## Variation - SAP ready PowerVS
{: #overview-sap-ready-powervs}

'SAP ready PowerVS' variation of '{{site.data.keyword.powerSysFull}} for SAP HANA' creates a basic and expandable SAP system landscape builds on the foundation of the [{{site.data.keyword.powerSysFull}} with VPC landing zone](/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. PowerVS instances for SAP HANA and SAP NetWeaver are deployed and preconfigured for SAP installation.

Services such as DNS, NTP and NFS running in VPC and provided by '{{site.data.keyword.powerSysFull}} with VPC landing zone' are leveraged.
Transit gateway provide the network bridge between the IBM Power infrastructure and the IBM VPC and public internet.
The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management and the network connectivity configuration provided by '{{site.data.keyword.powerSysFull}} with VPC landing zone'.

### Summary Outcome
{: #overview-sap-ready-powervs-summary-outcome}

SAP-tuned HANA and NetWeaver configuration to IBM PowerVS hosts

### Summary Tasks
{: #overview-sap-ready-powervs-summary-tasks}

-  Creates a new private subnet for SAP communication for the entire landscape.
-  Creates and configures one PowerVS instance for SAP HANA based on best practices.
-  Creates and configures multiple PowerVS instances for SAP NetWeaver based on best practices.
-  Creates and configures one optional PowerVS instance that can be used for sharing SAP files between other system instances.
-  Connects all created PowerVS instances to a proxy server specified by IP address or hostname.
-  Optionally connects all created PowerVS instances to an NTP server and DNS forwarder specified by IP address or hostname.
-  Optionally configures a shared NFS directory on all created PowerVS instances.
-  If more than one NetWeaver instance is selected, /sapmnt directory is exported as NFS share by primary instance and mounted on all other NetWeaver instances.
-  Post-instance provisioning, Ansible Galaxy collection roles from [IBM](https://galaxy.ansible.com/ui/repo/published/ibm/power_linux_sap/) are executed: `power_linux_sap`.
-  Tested with RHEL8.4/8.6/8.8/9.2/9.4, SLES15-SP3/SP5 images.

### Prerequisites
{: #overview-sap-ready-powervs-prerequisites}

1. If you do not have a [Standard Landscape Variation of {{site.data.keyword.powerSysFull}} with VPC landing zone deployment](/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) create it first.

### Notes
{: #overview-sap-ready-powervs-notes}

-  **Does not install any SAP software or solutions.**
-  Filesystem sizes for HANA data and HANA log are **calculated automatically** based on the **memory size**.
-  Custom storage configuration by providing custom volume size, **iops**(tier0, tier1, tier3, tier5k), counts and mount points is supported.
-  **Do not specify** a filesystem `/sapmnt` explicitly for NetWeaver instance, as a 300GB volume is automatically created on the primary NetWeaver instance.



## Variation - SAP S/4HANA or BW/4HANA
{: #overview-sap-s4hana-bw4hana}

SAP S/4HANA or BW/4HANA' variation of '{{site.data.keyword.powerSysFull}} for SAP HANA' creates a basic and expandable SAP system landscape builds on the foundation of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. PowerVS instances for SAP HANA, SAP NetWeaver and optionally for shared SAP files are deployed and preconfigured for SAP installation.

**S/4HANA or BW/4HANA solution is installed based on selected version.**
Services such as DNS, NTP and NFS running in VPC and provided by '{{site.data.keyword.powerSysFull}} with VPC landing zone' are leveraged.

Transit gateway provide the network bridge between the IBM Power infrastructure and the IBM VPC and public internet.
The resulting SAP landscape leverages the services such as Activity Tracker, Cloud Object Storage, Key Management and the network connectivity configuration provided by '{{site.data.keyword.powerSysFull}} with VPC landing zone'.

### Summary Outcome
{: #overview-sap-s4hana-bw4hana-summary-outcome}

SAP S/4HANA or SAP BW/4HANA installation configuration to IBM PowerVS hosts.

### Summary Tasks
{: #overview-sap-s4hana-bw4hana-summary-tasks}

- Creates a new private subnet for SAP communication for the entire landscape.
- Creates and configures one PowerVS instance for SAP HANA based on best practices for HANA database.
- Creates and configures one PowerVS instance for SAP NetWeaver based on best practices, hosting the PAS and ASCS instances.
- Creates and configures one optional PowerVS instance for sharing SAP files between other system instances.
- Connects all created PowerVS instances to a proxy server specified by IP address or hostname.
- Optionally connects all created PowerVS instances to an NTP server and DNS forwarder specified by IP address or hostname.
- Optionally configures a shared NFS directory on all created PowerVS instances.
- Supports installation of **S/4HANA2023, S/4HANA2022, S/4HANA2021, S/4HANA2020, BW/4HANA2021**.
- Supports installation using **Maintenance Planner** as well.


### Prerequisites
{: #overview-sap-s4hana-bw4hana-prerequisites}

1. If you do not have a [Standard Landscape Variation of {{site.data.keyword.powerSysFull}} with VPC landing zone deployment](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global?catalog_query=aHR0cHM6Ly9jbG91ZC5pYm0uY29tL2NhdGFsb2c%2Fc2VhcmNoPXBvd2VyI3NlYXJjaF9yZXN1bHRz) create it first.
1.  **It is required to have an existing IBM Cloud Object Storage (COS) instance**. Within the instance, an Object Storage Bucket containing the **SAP Software installation media files is required in the correct folder structure as defined**. Instructions can be found [here](/docs/sap-powervs?topic=sap-powervs-solution-create-cos-instance).


### Notes
{: #overview-sap-s4hana-bw4hana-notes}

- Filesystem sizes for HANA data and HANA log are **calculated automatically** based on the **memory size**.
- Custom storage configuration by providing custom volume size, **iops**(tier0, tier1, tier3, tier5k), counts and mount points is supported.
- **Do not specify** a filesystem `/sapmnt` explicitly for NetWeaver instance, as a 300GB volume is automatically created on the primary NetWeaver instance.
