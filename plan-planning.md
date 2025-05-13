---

copyright:
  years: 2023, 2025
lastupdated: "2025-05-12"
subcollection: sap-powervs
keywords: iam, permissions, plan, ssh key
content-type: tutorial
services: iam, apikey, sshkeys, DA
completion-time: 1h

---

{{site.data.keyword.attribute-definition-list}}

# Before you begin deploying
{: #powervs-automation-prereqs}
{: toc-content-type="tutorial"}
{: toc-services="iam, apikey, sshkeys, DA"}
{: toc-completion-time="1h"}


This tutorial walks through necessary steps required to be preformed which enables a user to successfully deploy the architecture.

## IAM Permissions
{: #solution-iam-permissions}
{: step}

IAM access roles are required to install this deployable architecture and create all the required elements.

You need the following permissions for this deployable architecture:

1. Create services from {{site.data.keyword.cloud_notm}} catalog.
1. Create and modify {{site.data.keyword.vpc_short}} services, virtual server instances, networks, network prefixes, storage volumes, SSH keys, and security groups of this VPC.
1. Create and modify {{site.data.keyword.powerSysShort}} services, virtual server instances, networks, storage volumes, ssh keys of this {{site.data.keyword.powerSysShort}}.
1. Create and modify {{site.data.keyword.cloud_notm}} direct links and {{site.data.keyword.tg_full_notm}}.
1. Access existing {{site.data.keyword.cos_short}} services.
1. The Editor role on the Projects service.
1. The Editor and Manager role on the Schematics service.
1. The Viewer role on the resource group for the project.

For information about configuring permissions, contact your {{site.data.keyword.cloud_notm}} account administrator.

## {{site.data.keyword.powerSysFull}} with VPC landing zone deployable architecture
{: #solution-landing-zone-da}
{: step}

1. You must have an existing deployment of [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture. This can be deployed from IBM catalog tile. Instructions are provided [here](/docs/powervs-vpc?topic=powervs-vpc-automation-solution-overview).

Only following variations are supported to proceed with the deployment of SAP Ready PowerVS and SAP S/4HANA or BW/4HANA.

- Create a new architecture: [Standard Variation](/docs/powervs-vpc?topic=powervs-vpc-deploy-arch-ibm-pvs-inf-standard)
- Extend {{site.data.keyword.powerSysFull}} with VPC landing zone: [Standard Variation](/docs/powervs-vpc?topic=powervs-vpc-deploy-arch-ibm-pvs-inf-extension)


The ID of this schematics workspace will be the pre-requisite workspace id required by '{{site.data.keyword.powerSysFull}} for SAP HANA' to create and configure the PowerVS instances for SAP on top of the existing infrastructure.

## Define hostnames
{: #solution-define-hostnames}
{: step}

Define hostnames for all the SAP services that you will deploy in the landscape. You will map the hostnames to the IP addresses later after the resources are provisioned. The domain name must be the same for all hostnames that belong to one SAP system.

## Determine size parameters
{: #solution-size-parameters}
{: step}

Determine the size parameters for each SAP workload that you plan to deploy. The most important parameters are memory size (especially for SAP HANA) and the number of SAPs. Most of the other configurations can be derived from these two key metrics.

For more information, see [Sizing process for SAP Systems](/docs/sap?topic=sap-sizing) and see [SAP Sizing](https://www.sap.com/about/benchmark/sizing.html).

For deployment of each SAP system, you must be aware about how many SAP NetWeaver instances you plan to deploy.

For deployment of each SAP NetWeaver PowerVS instance, you must be aware of the following sizing parameters:

- Memory size
- Number of CPUs

For deployment of SAP HANA PowerVS instance, you must be aware of the following sizing parameters:

- SAP t-shirt size as combination of memory and number of CPUs. Check for certified profiles [here](https://cloud.ibm.com/docs/sap?topic=sap-hana-iaas-offerings-profiles-power-vs)

## SAP software installation packages for the SAP S/4HANA or BW/4HANA variation only
{: #solution-sap-install-packages}
{: step}

You must have an existing IBM Cloud Object Storage instance.
{: important}

These steps apply to the SAP S/4HANA or BW/4HANA variation only.

1. Within the instance, an {{site.data.keyword.cos_short}} bucket that contains the SAP Software installation media files is required.
1. To configure access to these software packages from a running virtual server instance, you need the following information:
    - {{site.data.keyword.cos_short}} endpoint
    - {{site.data.keyword.cos_short}} bucket name
    - {{site.data.keyword.cos_short}} HMAC access key
    - {{site.data.keyword.cos_short}} HMAC secret access key

Follow the [tutorial here](/docs/sap-powervs?topic=sap-powervs-solution-create-cos-instance) which details the steps to create a Cloud Object Storage (COS) instance and organizing the SAP binaries in correct structure.

## Learn about deployment input parameters
{: #solution-input-parameters}
{: step}

Ensure that you are familiar with the required input for the deployment execution. See [description for input parameters](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-ready-to-go/README.md){: external}.

## Additional background information
{: #solution-prereqs-additional}

- [IBM {{site.data.keyword.powerSysFull}} s service documentation](/docs/power-iaas)
- [SAP on IBM Cloud documentation](/docs/sap)
- [Deployable architecture code](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap){: external}
- Main dependencies:
    - [Terraform IBM Module - PowerVS Infrastructure](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-infrastructure){: external}
    - [Terraform IBM Module - PowerVS Instance](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-instance){: external}
    - [IBM Power Linux SAP ansible galaxy role](https://galaxy.ansible.com/ibm/power_linux_sap){: external}
