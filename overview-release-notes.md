---

copyright:
  years: 2023, 2025
lastupdated: "2025-07-25"
subcollection: sap-powervs
content-type: release-note
keywords:

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture
{: #automation-solution-relnotes}

Use these release notes to learn about the latest updates to the {{site.data.keyword.powerSys_notm}} for SAP HANA. The entries are grouped by date.
{: shortdesc}

## July 2025
{: #sap-powervs-2025-07}

### 25 Jul 2025
{: #sap-powervs-jul25}
{: release-note}

Version 4.2.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 4.2.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Added support for s1022 in `us-south` and removed support for s922 in `us-south`.
    - NetWeaver instances are now created by default on Power 10 (s1022) in the following regions:`dal10, dal12, dal14, eu-de-1, eu-de-2, mad02, mad04, osa21, sao01, sao04, tok04, wdc06, wdc07, us-south`
    - In the following regions `s922` is used: `che01, lon04, lon06, mon01, syd04, syd05, tor01, us-east`

## May 2025
{: #sap-powervs-2025-05}

### 12 May 2025
{: #sap-powervs-may12}
{: release-note}

Version 4.2.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 4.2.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade TF provider `1.78.0`
    - Refactor custom image verification for SAP VM deployments.

## April 2025
{: #sap-powervs-2025-04}

### 22 April 2025
{: #sap-powervs-apr22}
{: release-note}

Version 4.1.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 4.1.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - NetWeaver instances are now created by default on Power 10 (s1022) in the following regions:`dal10, dal12, dal14, eu-de-1, eu-de-2, mad02, mad04, osa21, sao01, sao04, tok04, wdc06, wdc07`
    - In the following regions `s922` is used: `che01, lon04, lon06, mon01, syd04, syd05, tor01, us-east, us-south`
    - upgrade powervs-instance to `2.6.1`

### 03 April 2025
{: #sap-powervs-apr03}
{: release-note}

Version 4.0.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 4.0.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - The {{site.data.keyword.powerSysFull}} instance used for file sharing has been removed
    - For 'SAP ready PowerVS' variation only: if more than 1 NetWeaver instance is selected, `/sapmnt` directory is exported by the primary NetWeaver instance as NFS share and mounted on all other NetWeaver instances

[Warning]{: tag-red}
: Version 4.0.0 includes backward-incompatible changes.
    - The {{site.data.keyword.powerSysFull}} instance used for file sharing has been removed and upgrading from an old version will lead to the data stored on the instance being lost.
    - Do not upgrade to this version if there were previous deployments.
    - Use this for new deployments only.

## March 2025
{: #sap-powervs-2025-03}

### 27 March 2025
{: #sap-powervs-mar27}
{: release-note}

Version 3.6.3 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.6.3 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Add validation for hana instance hostname length to not exceed 13 characters, as required by the sap preconfigure ansible roles
    - Update default SLES image to SLES15-SP6

### 21 March 2025
{: #sap-powervs-mar21}
{: release-note}

Version 3.6.2 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.6.2 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - New feature [**{{site.data.keyword.sysdigsecure_full}}**](/docs/workload-protection?topic=workload-protection-key-features) instance and Sysdig agent installation on all {{site.data.keyword.powerSysShort}} instances. {{site.data.keyword.sysdigsecure_full}} helps to find and prioritize software vulnerabilities, detect and respond to threats, and manage configurations, permissions, and compliance from source to run.
    - The deployable architecture picks up details from landing zone deployment and installs and sets up Sysdig agent on the {{site.data.keyword.powerSys_notm}} instances if {{site.data.keyword.sysdigsecure_short}} is enabled in the landing zone

## February 2025
{: #sap-powervs-2025-02}

### 24 February 2025
{: #sap-powervs-feb24}
{: release-note}

Version 3.5.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.5.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Support BYOL and Bring Your Own Images for SAP HANA and SAP NETWEAVER.
    - Ensured the use of a strong Ansible Vault password with 15-100 characters, including at least one uppercase letter, one lowercase letter, one number, and one special character from the allowed set: !#$%&()*+-.:;&lt;=&gt;?@[]_{|}~.
    - Upgrade IBM TF provider to `1.75.2`

## January 2025
{: #sap-powervs-2025-01}

### 15 January 2025
{: #sap-powervs-jan15}
{: release-note}

Version 3.4.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.4.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - New feature **Integration with IBM Cloud Monitoring Service: SAP Dashboards**
    - When a Monitoring Instance and monitoring host are deployed using the {{site.data.keyword.powerSys_notm}} with the VPC landing zone deployable architecture standard variation, the S/4HANA or BW/4HANA solution now supports the export of HANA database and SAP System metrics. These metrics are seamlessly integrated and displayed on the IBM Cloud Monitoring Dashboard.
    - Upgrade IBM terraform provider version to `1.74.0`


## December 2024
{: #sap-powervs-2024-12}

### 13 December 2024
{: #sap-powervs-dec13}
{: release-note}

Version 3.3.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.3.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade minimum version for power_linux_sap roles to `v3.0.0`
    - Upgrade IBM terraform provider version to `1.71.3`
    - Added checks for Full Linux subscription
    - Add input validation for sap solution variables
    - Remove ansible collection version dependencies from scripts instead install collection dependencies from ansible galaxy requirements.yml
    - Support SAP deployments in `lon04` DC
    - Requires [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} version `>= 8.0.0`

## November 2024
{: #sap-powervs-2024-11}

### 11 November 2024
{: #sap-powervs-nov11}
{: release-note}

Version 3.1.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 3.1.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade ibm tf provider version to `1.70.0`
    - Upgrade minimum tf provider version to `1.9.0`
    - Support `Mad02` DC

## June 2024
{: #sap-powervs-2024-06}

### 10 June 2024
{: #sap-powervs-jun10}
{: release-note}

Version 2.1.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 2.1.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Fixes HANA AFL additional installation by installing missing `glibc-langpack-en` package.

### 07 June 2024
{: #sap-powervs-jun07}
{: release-note}

Version 2.1.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 2.1.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Supports `S/4HANA 2023`
    - Storage requirements for HANA DATA and log filesystem has been updated based on SAP release notes in March 2024. Now the storage is calculated with a factor of `1.5 x Memory` instead of `1.2 x Memory`

## May 2024
{: #sap-powervs-2024-05}

### 31 May 2024
{: #sap-powervs-may31}
{: release-note}

Version 2.0.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 2.0.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Please refer release notes v2.0.0
    - Upgraded ansible collection `ibm.power_linux_sap` version to `v2.1.1` that fixes SLES OS initialization.


### 26 May 2024
{: #sap-powervs-may26}
{: release-note}

Version 2.0.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 2.0.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Does not support upgrade process from previous version 1.x.x to 2.0.0.
    - Requires {{site.data.keyword.powerSysFull}} with VPC landing zone version `>5.0.0`.
    - New Central Ansible node on landing zone.
    - Switch ansible playbook execution from localhost to target host.
    - Switched from community `sap_swpm` role to [RHEL linux system SAP roles](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux_for_sap_solutions/8/html-single/red_hat_enterprise_linux_system_roles_for_sap/index)
    - Removed cloud connection support.
    - Supports `RHEL8.8/9.2 SAP` FLS(Full linux subscription) images.
    - Private SSH keys **must be passed as it is**. Doesn't support here doc string format anymore.

[Warning]{: tag-red}
: Version 2.0.0 includes backward-incompatible changes.
    - Do not upgrade to this version if there were previous deployments.
    - Use this for new deployments only.

### 11 May 2024
{: #sap-powervs-may11}
{: release-note}

Version 1.11.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 1.11.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Toronto 01 `tor01` DC to PER. New deployments in Toronto 01 region will make use of PER.
    - Upgrade US-south `us-south` DC to PER. New deployments in Us-south region will make use of PER.

[Warning]{: tag-red}
: Version 1.11.0 includes backward-incompatible changes for `tor01` and `us-south` DCs only.
    - Do not upgrade to this version if previous deployments were made in `tor01` and `us-south` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in `tor01` and `us-south` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

### 2 May 2024
{: #sap-powervs-may2}
{: release-note}

Version 1.10.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 1.10.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Sydney 04 `syd04` DC to PER. New deployments in Sydney 04 region will make use of PER.

[Warning]{: tag-red}
: Version 1.10.0 includes backward-incompatible changes for Sydney 04 `syd04` DC only.
    - Do not upgrade to this version if previous deployments were made in Sydney 04 `syd04` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Sydney 04 `syd04` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

## April 2024
{: #sap-powervs-2024-04}

### 14 April 2024
{: #sap-powervs-apr14}
{: release-note}

Version 1.9.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 1.9.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade `tok04`, `osa21`, `lon06` and `syd05` DCs to PER. New deployments in these regions will make use of PER.
    - Improved automatic storage based on memory usage making use of fixed iops and other tiers for data, log and shared disks.
    - Allows user to reapply on failed execution in case of using wrong credentials for COS to download the binaries.
    - Upgraded IBM terraform provider version to `1.64.1`

[Warning]{: tag-red}
: Version 1.9.0 includes backward-incompatible changes for Sao Paulo 01 `tok04`, `osa21`, `lon06` and `syd05` DCs only.
    - Do not upgrade to this version if previous deployments were made in `tok04`, `osa21`, `lon06` and `syd05` {{site.data.keyword.powerSys_notm}} zones as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in `tok04`, `osa21`, `lon06` and `syd05` {{site.data.keyword.powerSys_notm}} zones.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

## February 2024
{: #sap-powervs-2024-02}

### 7 February 2024
{: #sap-powervs-feb7}
{: release-note}

Version 1.8.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 1.8.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Sao Paulo 01 `sao01` DC to PER. New deployments in Sao Paulo 01 region will make use of PER.

[Warning]{: tag-red}
: Version 1.8.0 includes backward-incompatible changes for Sao Paulo 01 `sao01` DC only.
    - Do not upgrade to this version if previous deployments were made in Sao Paulo 01 `sao01` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Sao Paulo 01 `sao01` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.


### 1 February 2024
{: #sap-powervs-feb1}
{: release-note}

Version 1.7.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
: Version 1.7.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Dallas 12 `dal12` DC to PER. New deployments in Dallas 12 region will make use of PER.

[Warning]{: tag-red}
: Version 1.7.0 includes backward-incompatible changes for Dallas 12 `dal12` DC only.
    - Do not upgrade to this version if previous deployments were made in Dallas 12 `dal12` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER.
    - Use this for new deployments in Dallas 12 `dal12` {{site.data.keyword.powerSys_notm}} zone.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.

## January 2024
{: #sap-powervs-2024-01}

### 30 January 2024
{: #sap-powervs-jan30}
{: release-note}

Version 1.6.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
:   Version 1.6.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Fixes SAP SWPM hdbuserstore config by setting correct port for proper communication between Netweaver instance and HANA DB host. This fix is applicable for `S/4HANA and BW/4HANA solution` variation only.


### 12 January 2024
{: #sap-powervs-jan12}
{: release-note}

Version 1.6.0 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
:   Version 1.6.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` DCs to PER.
    - Enable support for `SAO04` PER datacenter.

[Warning]{: tag-red}
: Version 1.6.0 includes backward-incompatible changes for Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` DCs only .
    - Do not upgrade to this version if previous deployments were made in Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` {{site.data.keyword.powerSys_notm}} zone as doing so will corrupt the landscape because of switch from Cloud connections to PER. This will not convert old workspaces into PER enabled workspaces.
    - Use this version for new deployments in Frankfurt 1 `eu-de-1` and Frankfurt 2 `eu-de-2` {{site.data.keyword.powerSys_notm}} zones.
    - Deployments done in other {{site.data.keyword.powerSys_notm}} zone can be upgraded with any issue.


### 08 January 2024
{: #sap-powervs-jan08}
{: release-note}

Version 1.5.1 of the {{site.data.keyword.powerSysFull}} for {{site.data.keyword.powerSys_notm}} for SAP HANA deployable architecture is available
:   Version 1.5.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Upgrade terraform IBM provider version to `1.61.0`

## November 2023
{: #sap-powervs-2023-11}

### 22 November 2023
{: #sap-powervs-nov22}
{: release-note}

Version 1.4.0 available
:   Version 1.4.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` or higher of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Support `WDC06` data center which is [PER enabled](/docs/power-iaas?topic=power-iaas-per).


### 10 November 2023
{: #sap-powervs-nov10}
{: release-note}

Version 1.3.0 available
:   Version 1.3.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - New variation **'SAP S/4HANA or BW/4HANA'** solution is now supported and can be consumed from the deployable architecture.


### 09 November 2023
{: #sap-powervs-nov09}
{: release-note}

Version 1.2.1 available
:   Version 1.2.1 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Fixes missing readme file required for OS registration in few DCs on HANA instance which errors rarely.


### 03 November 2023
{: #sap-powervs-nov03}
{: release-note}

Version 1.2.0 available
:   Version 1.2.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - This version requires `v3.0.0` of [{{site.data.keyword.powerSys_notm}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global){: external} deployable architecture.
    - Upgrade *terraform-ibm-modules/powervs-instance/ibm* version to `1.0.2`
    - Refactor modules.
    - Cores, memory and processor type can now be set for sharefs instance.

## September 2023
{: #sap-powervs-2023-09}

### 06 September 2023
{: #sap-powervs-sep06}
{: release-note}

Version 1.1.0 available
:   Version 1.1.0 of the [{{site.data.keyword.powerSys_notm}} for SAP HANA](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global){: external} deployable architecture is available in the {{site.data.keyword.cloud_notm}} [catalog](/catalog#reference_architecture){: external}.
    - Support for `DAL10` DC enabled where `PER` is supported.
    - Update OS registration scripts to support PER and NON PER DC
    - Add nfs export for sharefs PowerVS instance
    - Support RHEL8.6 and SLES15.4 SAP images
