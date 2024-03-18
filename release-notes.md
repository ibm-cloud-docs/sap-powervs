---

copyright:
  years: 2024
lastupdated: "2024-02-07"

keywords:

subcollection: sap-powervs

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture
{: #sap-powervs-relnotes}

Use these release notes to learn about the latest updates to the {{site.data.keyword.powerSys_notm}} for SAP HANA. The entries are grouped by date.
{: shortdesc}

## 18 March 2024
{: #powervs-vpc-mar18}
{: release-note}

Version 1.9.0 of the available
: Version 1.9.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Tokyo 04 `tok04` DC to PER. New deployments in Tokyo region will make use of PER.

[Warning]{: tag-red}
: Version 1.9.0 includes backward-incompatible changes for Tokyo 04 `tok04` DC only. 
    - Do not upgrade to this version if previous deployments were made in Tokyo 04 `tok04` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Tokyo 04 `tok04` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

## 7 February 2024
{: #powervs-vpc-feb7}
{: release-note}

Version 1.8.0 of the available
: Version 1.8.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Sao Paulo 01 `sao01` DC to PER. New deployments in Sao Paulo 01 region will make use of PER.

[Warning]{: tag-red}
: Version 1.8.0 includes backward-incompatible changes for Sao Paulo 01 `sao01` DC only. 
    - Do not upgrade to this version if previous deployments were made in Sao Paulo 01 `sao01` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Sao Paulo 01 `sao01` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.


## 1 February 2024
{: #powervs-vpc-feb1}
{: release-note}

Version 1.7.0 of the available
: Version 1.7.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Dallas 12 `dal12` DC to PER. New deployments in Dallas 12 region will make use of PER.

[Warning]{: tag-red}
: Version 1.7.0 includes backward-incompatible changes for Dallas 12 `dal12` DC only. 
    - Do not upgrade to this version if previous deployments were made in Dallas 12 `dal12` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Dallas 12 `dal12` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

## 30 January 2024
{: #powervs-vpc-jan30}
{: release-note}

Version 1.6.1 of the available
:   Version 1.6.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Fixes SAP SWPM hdbuserstore config by setting correct port for proper communication between Netweaver instance and HANA DB host. This fix is applicable for `S/4HANA and BW/4HANA solution` variation only.


## 12 January 2024
{: #powervs-vpc-jan12}
{: release-note}

Version 1.6.0 of the available
:   Version 1.6.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` DCs to PER.
    - Enable support for `SAO04` PER datacenter.

[Warning]{: tag-red}
: Version 1.6.0 includes backward-incompatible changes for Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` DCs only . 
    - Do not upgrade to this version if previous deployments were made in Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER. This will not convert old workspaces into PER enabled workspaces.
    - Use this version for new deployments in Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` {{site.data.keyword.powerSys_notm}} zones.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.


## 08 January 2024
{: #powervs-vpc-jan08}
{: release-note}

Version 1.5.1 of the available
:   Version 1.5.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade terraform IBM provider version to `1.61.0`


## 22 November 2023
{: #sap-powervs-nov22}
{: release-note}

Version 1.4.0 available
:   Version 1.4.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` or higher of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Support `WDC06` data center which is [PER enabled](/docs/power-iaas?topic=power-iaas-per).


## 10 November 2023
{: #sap-powervs-nov10}
{: release-note}

Version 1.3.0 available
:   Version 1.3.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - New variation **'SAP S/4HANA or BW/4HANA'** solution is now supported and can be consumed from the deployable architecture.


## 09 November 2023
{: #sap-powervs-nov09}
{: release-note}

Version 1.2.1 available
:   Version 1.2.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Fixes missing readme file required for OS registration in few DCs on HANA instance which errors rarely.


## 03 November 2023
{: #sap-powervs-nov03}
{: release-note}

Version 1.2.0 available
:   Version 1.2.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
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
