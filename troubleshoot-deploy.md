---

copyright:
  years: 2023
lastupdated: "2023-07-10"

keywords: 

subcollection: sap-powervs

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}


# My deployment failed, how do I proceed?
{: #troubleshoot-deploy}
{: troubleshoot}

Your deployment failed.
{: shortdesc}

You attempted to deploy an instance of the Power Virtual Server for SAP HANA deployable architecture but it failed.
{: tsSymptoms}

As part of the development of the deployable architecture we verify the workflows described in this guide continuously. In the stable {{site.data.keyword.cloud_notm}} environment, no errors are expected. But because there are several infrastructure layers and components included in the deployment, there is a possibility for issues that aren't anticipated. For example, the maintenance activity in the particular data center, errors in the VPC, PowerVS or network services, or issues in OS software updates can cause deployment failures.
{: tsCauses}

If the deployment process does not finish successfully, we recommend first looking at the {{site.data.keyword.bplong_notm}} logs. These logs typically provide the information about the component that causes the issue. 
{: tsResolve}

- Ensure that all prerequisites are applied according to the [planning guide](/docs/sap-powervs?topic=sap-powervs-sap-powervs-automation-planning)
- Verify that correct input parameters are provided as described in the [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/examples/ibm-catalog/deployable-architectures/sap-ready-to-go/README.md){: external}

If you still cannot solve your issue, open a case in the {{site.data.keyword.cloud_notm}} support center.
