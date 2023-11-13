---

copyright:
  years: 2023
lastupdated: "2023-11-10"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Before you begin deploying the Power Virtual Server for SAP HANA deployable architecture
{: #sap-powervs-automation-planning}

This deployment guide covers prerequisite for Power Virtual Server for SAP HANA deployable architecture.
{: shortdesc}

## Confirm your {{site.data.keyword.cloud_notm}} settings
{: #vpc-cloud-prereqs}

Complete the following steps before you deploy the Power Virtual Server with VPC landing zone deployable architecture.

1.  Confirm or set up an {{site.data.keyword.cloud_notm}} account:

    Make sure that you have an {{site.data.keyword.cloud_notm}} Pay-As-You-Go or Subscription account:

    - If you don't have an {{site.data.keyword.cloud_notm}} account, [create one](/docs/account?topic=account-account-getting-started).
    - If you have a Trial or Lite account, [upgrade your account](/docs/account?topic=account-upgrading-account).
1.  Configure your {{site.data.keyword.cloud_notm}} account:
    1.  Log in to [{{site.data.keyword.cloud_notm}}](https://cloud.ibm.com){: external} with the {{site.data.keyword.ibmid}} you used to set up the account. This {{site.data.keyword.ibmid}} user is the account owner and has full IAM access.
    1.  [Complete the company profile](/docs/account?topic=account-contact-info) and contact information for the account. This profile is required to stay in compliance with {{site.data.keyword.cloud_notm}} Financial Services profile.
    1.  [Enable the Financial Services Validated option](/docs/account?topic=account-enabling-fs-validated) for your account.
    1.  Enable virtual routing and forwarding (VRF) and service endpoints by creating a support case. Follow the instructions in [enabling VRF and service endpoints](/docs/account?topic=account-vrf-service-endpoint&interface=ui#vrf).

## Set the IAM permissions
{: #powervs-automation-IAM-prereqs}

Set up account access ({{site.data.keyword.iamshort}} (IAM)):
- Create an {{site.data.keyword.cloud_notm}} [API key](/docs/account?topic=account-userapikey#create_user_key). The user who owns this key must have the Administrator role.

    Service ID API keys are not supported for the Red Hat OpenShift Container Platform on VPC landing zone deployable architecture.
    {: tip}

- For compliance with {{site.data.keyword.framework-fs_notm}}, users in your account are required to use [multi-factor authentication (MFA)](/docs/account?topic=account-account-getting-started#account-gs-mfa).
- [Set up access groups](/docs/account?topic=account-accoungetting-started#account-gs-accessgroups).

    User access to {{site.data.keyword.cloud_notm}} resources is controlled by using the access policies that are assigned to access groups. For {{site.data.keyword.cloud_notm}} Financial Services validation, do not assign direct IAM access to any {{site.data.keyword.cloud_notm}} resources.

    Select **All Identity and Access enabled services** when you assign access to the group.

### Verify access roles
{: #vpc-access-roles}

IAM access roles are required to install this deployable architecture and create all the required elements.

You need the following permissions for this deployable architecture:

- Create services from {{site.data.keyword.cloud_notm}} catalog.
- Create and modify {{site.data.keyword.vpc_short}} services, virtual server instances, networks, network prefixes, storage volumes, SSH keys, and security groups of this VPC.
- Create and modify {{site.data.keyword.powerSysShort}} services, virtual server instances, networks, storage volumes, ssh keys of this {{site.data.keyword.powerSysShort}}.
- Create and modify {{site.data.keyword.cloud_notm}} direct links and {{site.data.keyword.tg_full_notm}}.
- Access existing {{site.data.keyword.cos_short}} services.

For information about configuring permissions, contact your {{site.data.keyword.cloud_notm}} account administrator.

### Access for {{site.data.keyword.cloud_notm}} projects
{: #access-projects}

You can use {{site.data.keyword.cloud_notm}} projects as a deployment option. Projects are designed with infrastructure as code and compliance in mind to help ensure that your projects are managed, secure, and always compliant. For more information, see [Learn about IaC deployments with projects](/docs/secure-enterprise?topic=secure-enterprise-understanding-projects).

You need the following access to create a project and create project resources within the account. Make sure that you have the following access:

- The Editor role on the Projects service
- The Editor and Manager role on the {{site.data.keyword.bpshort}} service
- The Viewer role on the resource group for the project

For more information, see [Assigning users access to projects](/docs/secure-enterprise?topic=secure-enterprise-access-project).

## For the SAP S/4HANA or BW/4HANA variation SAP software installation packages
{: #sap-powervs-automation-sap-install-packages}

You must have an existing IBM Cloud Object Storage instance.
{: important}

These steps apply to the SAP S/4HANA or BW/4HANA variation only.

1. Within the instance, an {{site.data.keyword.cos_short}} bucket that contains the SAP Software installation media files is required. Follow the folder structure as defined in the [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-s4hana-bw4hana/README.md#2-sap-binaries-required-for-installation-and-folder-structure-in-ibm-cloud-object-storage-bucket){: external}.
1. To configure access to these software packages from a running virtual server instance, you need the following information:
    - {{site.data.keyword.cos_short}} endpoint
    - {{site.data.keyword.cos_short}} bucket name
    - {{site.data.keyword.cos_short}} HMAC access key
    - {{site.data.keyword.cos_short}} HMAC secret access key

For more information about configuring API access in {{site.data.keyword.cos_short}}, see the [Getting started with IBM Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage) and [Service credentials](/docs/cloud-object-storage?topic=cloud-object-storage-service-credentials) documentation.

## Define hostnames
{: #sap-powervs-automation-define-hostnames}

Define hostnames for all the SAP services that you will deploy in the landscape. You will map the hostnames to the IP addresses later after the resources are provisioned. The domain name must be the same for all hostnames that belong to one SAP system.

## Determine size parameters
{: #sap-powervs-automation-size-parameters}

Determine the size parameters for each SAP workload that you plan to deploy. The most important parameters are memory size (especially for SAP HANA) and the number of SAPs. Most of the other configurations can be derived from these two key metrics.

For more information, see [Sizing process for SAP Systems](/docs/sap?topic=sap-sizing) and see [SAP Sizing](https://service.sap.com/quicksizer).

For deployment of each SAP system, you must be aware about how many SAP NetWeaver instances you plan to deploy. Decide whether you plan to use a separate PowerVS instance for hosting SAP shared files.

For deployment of each SAP NetWeaver PowerVS instance, you must be aware of the following sizing parameters:

- Memory size
- Number of CPUs

For deployment of SAP HANA PowerVS instance, you must be aware of the following sizing parameters:

- SAP t-shirt size as combination of memory and number of CPUs

## Learn about deployment input parameters
{: #sap-powervs-automation-input-parameters}

Ensure that you are familiar with the required input for the deployment execution. See [description for input parameters](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/examples/ibm-catalog/deployable-architectures/sap-ready-to-go/README.md){: external}.

## Other background information
{: #sap-power-automation-prereqs-additional}

- [IBM Power Systems Virtual Servers service documentation](/docs/power-iaas)
- [SAP on IBM Cloud documentation](/docs/sap)
- [Deployable architecture code](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap){: external}
- Main dependencies:
    - [https://github.com/terraform-ibm-modules/terraform-ibm-powervs-infrastructure](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-infrastructure){: external}
    - [https://galaxy.ansible.com/ibm/power_linux_sap](https://galaxy.ansible.com/ibm/power_linux_sap){: external}
    - [https://galaxy.ansible.com/community/sap_install](https://galaxy.ansible.com/community/sap_install){: external}
