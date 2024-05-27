---

copyright:
  years: 2024
lastupdated: "2024-05-27"

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

If the deployment process does not finish successfully, look at the {{site.data.keyword.bplong_notm}} logs. These logs typically provide the information about the component that causes the issue.
{: tsResolve}

- Ensure that all prerequisites are applied according to the [planning guide](/docs/sap-powervs?topic=sap-powervs-plan)
- Verify that the input parameters for the SAP ready PowerVS variation are correct. The parameters are described in this [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-ready-to-go/README.md){: external}.
- Verify that the input parameters for the SAP S/4HANA or BW/4HANA variation are correct. The parameters are described in this [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-s4hana-bw4hana/README.md){: external}.

If you still cannot solve your issue, open a case in the {{site.data.keyword.cloud_notm}} support center.
