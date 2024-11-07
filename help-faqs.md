---

copyright:
  years: 2023, 2024
lastupdated: "2024-11-07"
subcollection: sap-powervs
content-type: faq
keywords:

---


{{site.data.keyword.attribute-definition-list}}



# FAQs for {{site.data.keyword.powerSysFull}} for SAP HANA deployable architecture
{: #automation-faqs}

FAQs for the {{site.data.keyword.powerSysFull}} for SAP HANA deployable architecture. To find all FAQs for {{site.data.keyword.cloud}}, see the [FAQ library](/docs/faqs).
{: shortdesc}

## What is a deployable architecture?
{: #what-is-da}
{: faq}

A deployable architecture is a combination of capabilities from one or more technologies that solve a customer-defined problem, and it can have one or more reference architectures based on the customer business needs. For more information about deployable architectures, see [What are modules and deployable architectures?](/docs/secure-enterprise?topic=secure-enterprise-understand-module-da) and read about [infrastructure architectures](/docs/overview?topic=overview-secure-enterprise#define-architecture) in "Running secure enterprise workloads on IBM Cloud".

## What is infrastructure as code?
{: #what-is-iac}
{: faq}

Infrastructure as code (IaC) is code to manage and provision infrastructure (for example, networks, virtual machines, load-balancers, clusters, services, and connection topology) in a descriptive model rather than by using manual processes.

With IaC, code defines your infrastructure, specifying your resources and their configuration. Your infrastructure code is treated the same as app code so that you can apply DevOps core practices such as version control, testing, and continuous monitoring. The {{site.data.keyword.powerSysFull}} with VPC landing zone architectures use [Terraform](https://www.terraform.io/){: external} to specify the infrastructure and [{{site.data.keyword.bplong_notm}}](/docs/schematics?topic=schematics-getting-started) to manage the deployment.

## How do I estimate costs?
{: #what-is-project-cost}
{: faq}

You can view and estimate of starting costs for a variation of the deployable architecture from the {{site.data.keyword.cloud_notm}} catalog details page. When you deploy by using {{site.data.keyword.cloud}} projects, the starting costs for the project are estimated from the validation window after your changes to the configuration are saved and validated.

## What does it mean for a deployable architecture to be SAP-certified?
{: #automation-fs-sap-validated}
{: faq}

SAP-certified designates that the deployable architecture creates services that are certified by SAP to run SAP HANA-based systems for production. For more information, see [{{site.data.keyword.cloud_notm}} documentation for SAP](/docs/sap).

## How long does the deployment take?
{: #automation-fs-sap-duration}
{: faq}

The length of the deployment process depends on the daily {{site.data.keyword.cloud_notm}} data center utilization and on the size and number of PowerVS instances. Usually, a deployment of one SAP system from the SAP ready PowerVS variation takes up to 1 hour and up to 2 hours for the SAP S/4HANA or BW/4HANA variation.

## Why certain IBM Cloud data centers might not be available?
{: #automation-fs-sap-dc-selection}
{: faq}

This deployable architecture ensures certain level of quality. Every data center is verified by a quality and assurance framework before it is made available. The list of supported data centers is regularly extended after all SAP-related verifications are completed.

## Are new releases compatible with previous ones?
{: #what-is-compatible}
{: faq}

Changes adhere to semantic versioning, with releases labeled as `{major}.{minor}.{patch}`. For more information, see the [release compatibility](https://terraform-ibm-modules.github.io/documentation/#/versioning){: external} in the {{site.data.keyword.cloud_notm}} Terraform modules documentation.
