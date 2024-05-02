---

copyright:
  years: 2024
lastupdated: "2023-07-10"

subcollection: sap-powervs

keywords:

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when you use Power Virtual Server for SAP HANA deployable architecture
{: #automation-solution-responsibilities}

Learn about the management responsibilities and terms and conditions that you have when you use the Power Systems Virtual Server for SAP HANA deployable architecture.
{: shortdesc}

- For more information about the responsibilities for you and for {{site.data.keyword.IBM}} when you use a deployable architecture, see [Understanding your responsibilities when you use deployable architectures](/docs/secure-enterprise?topic=secure-enterprise-responsibilities-deployable-architectures).
- For a high-level view of the service types in {{site.data.keyword.cloud}} and the breakdown of responsibilities between the customer and {{site.data.keyword.IBM_notm}} for each type, see [Shared responsibilities for using {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).
- For the overall terms of use, see [{{site.data.keyword.cloud}} Terms and Notices](/docs/overview?topic=overview-terms).

Review the following section for the specific responsibilities for you and for {{site.data.keyword.IBM_notm}} when you use the Power Systems Virtual Server for SAP HANA deployable architecture.

## Security and regulation compliance
{: #automation-solution-security}

Security and regulation compliance includes tasks such as security controls implementation and compliance certification.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Ensure that the operating system image does not contain any vulnerabilities. | IBM Cloud provided and verified RHEL and SLES operating system images are used. After deployment, operating system images are updated to the newest state in the defined minor release. Official RHEL and SLES software repositories are used for installation of additional software components (like SQUID proxy). | Customer is responsible to keep the operating system secure and compliant after deployment. |
| Ensure that the SAP software does not contain any vulnerabilities. | N/A | Customer is responsible to provide the SAP software. Customer is responsible to keep the SAP software secure and compliant after deployment. |
{: caption="Table 1. Security and compliance responsibilities for provisioned components}
