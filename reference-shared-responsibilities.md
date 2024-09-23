---

copyright:
  years: 2023, 2024
lastupdated: "2024-09-23"
subcollection: sap-powervs
keywords:

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when you use Power Virtual Server for SAP HANA deployable architecture
{: #shared-resp}

Learn about the management responsibilities and terms and conditions that you have when you use the Power Systems Virtual Server for SAP HANA deployable architecture.
{: shortdesc}

- For more information about the responsibilities for you and for {{site.data.keyword.IBM}} when you use a deployable architecture, see [Understanding your responsibilities when you use deployable architectures](/docs/secure-enterprise?topic=secure-enterprise-responsibilities-deployable-architectures).
- For a high-level view of the service types in {{site.data.keyword.cloud}} and the breakdown of responsibilities between the customer and {{site.data.keyword.IBM_notm}} for each type, see [Shared responsibilities for using {{site.data.keyword.cloud}} products](/docs/overview?topic=overview-shared-responsibilities).
- For the overall terms of use, see [{{site.data.keyword.cloud_notm}} Terms and Notices](/docs/overview?topic=overview-terms).
- For more information about the shared responsibilities for each Financial Services Validated service, see [Responsibilities for operating services in your deployment](/docs/framework-financial-services?topic=framework-financial-services-shared-responsibilities) in {{site.data.keyword.framework-fs_full}}.

Review the following section for the specific responsibilities for you and for {{site.data.keyword.IBM_notm}} when you use the Power Virtual Server for SAP HANA deployable architecture.

## Incident and operations management
{: #incident-and-ops}

Incident and operations management includes tasks such as monitoring, event management, high availability, problem determination, recovery, and full state backup and recovery.

This deployable architectures do not identify specific responsibilities in this area.

## Identity and access management
{: #iam-responsibilities}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|------|-------------------------------------------------|-----------------------|
| Secure with least privilege | Document the minimal IAM access requirements to run the deployable architecture. |  |
| Manage secrets | | * Generate the necessary secrets (for example, IAM API keys, SSH keys) that are required for the deployable architecture.  \n * Manage generated secrets by following secure best practices. |
{: row-headers}
{: caption="Table 3. Responsibilities for identity and access management" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}

## Security and regulation compliance
{: #automation-solution-security}

Security and regulation compliance includes tasks such as security controls implementation and compliance certification.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Ensure that the operating system image does not contain any vulnerabilities. | IBM Cloud provided and verified RHEL and SLES operating system images are used. After deployment, operating system images are updated to the newest state in the defined minor release. Official RHEL and SLES software repositories are used for installation of additional software components (like SQUID proxy). | Customer is responsible to keep the operating system secure and compliant after deployment. |
| Ensure that the SAP software does not contain any vulnerabilities. | N/A | Customer is responsible to provide the SAP software. Customer is responsible to keep the SAP software secure and compliant after deployment. |
{: caption="Table 1. Security and compliance responsibilities for provisioned components}
