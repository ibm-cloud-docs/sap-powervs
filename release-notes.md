---

copyright:
  years: 2023
lastupdated: "2023-11-03"

keywords: 

subcollection: sap-powervs

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture
{: #sap-powervs-relnotes}

Use these release notes to learn about the latest updates to the {{site.data.keyword.powerSys_notm}} for SAP HANA. The entries grouped by date.
{: shortdesc}

## 09 November 2023
{: #sap-powervs-nov09}
{: release-note}
Version 1.2.1 available
:   Version 1.2.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [Power Virtual Server with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Fixes missing readme File required for OS registration in few DCs on HANA instance which errors rarely.


## 03 November 2023
{: #sap-powervs-nov03}
{: release-note}
Version 1.2.0 available
:   Version 1.2.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [Power Virtual Server with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Upgrade *terraform-ibm-modules/powervs-instance/ibm* version to `1.0.2`
    - Refactor modules.
    - Cores, memory and processor type can now be set for sharefs instance.


## 06 September 2023
{: #sap-powervs-sep06}
{: release-note}
Version 1.1.0 available
:   Version 1.1.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Support for `DAL10` DC enabled where `PER` is supported.
    - Update OS registration scripts to support PER and NON PER DC
    - Add nfs export for sharefs PowerVS instance
    - Support RHEL8.6 and SLES15.4 SAP images


## 30 April 2023
{: #sap-powervs-apr30}
{: release-note}
Version 1.0.0 available
:   Version 1.0.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Introduced the solution. You can use the deployable architecture to create a {{site.data.keyword.powerSys_notm}} for SAP HANA landscape.
