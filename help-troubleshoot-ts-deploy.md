---

copyright:
  years: 2023, 2024
lastupdated: "2024-11-07"
subcollection: sap-powervs
content-type: troubleshoot
keywords:

---

{{site.data.keyword.attribute-definition-list}}


# My deployment failed, how do I proceed?
{: #ts-deploy}
{: troubleshoot}

Your deployment failed.
{: shortdesc}

You attempted to deploy an instance of the {{site.data.keyword.powerSysFull}} for SAP HANA deployable architecture but it failed.
{: tsSymptoms}

As part of the development of the deployable architecture we verify the workflows described in this guide continuously. In the stable {{site.data.keyword.cloud_notm}} environment, no errors are expected. But because there are several infrastructure layers and components included in the deployment, there is a possibility for issues that aren't anticipated. For example, the maintenance activity in the particular data center, errors in the VPC, PowerVS or network services, or issues in OS software updates can cause deployment failures.
{: tsCauses}

If the deployment process does not finish successfully, look at the {{site.data.keyword.bplong_notm}} logs. These logs typically provide the information about the component that causes the issue.

If you can't deploy successfully, follow these steps:

1.  Make sure that you comply with the prerequisites in the [planning](/docs/powervs-vpc?topic=powervs-vpc-powervs-automation-prereqs) topic.
1.  Check the values of the inputs.

    For example, from the **Configurations** tab in your project, click the name of your deployable architecture > **Edit**.
1.  Rerun the Schematics apply action again in {{site.data.keyword.bplong_notm}} by clicking **Apply plan** or by running the `ibmcloud schematics apply` command.

    1.  In the {{site.data.keyword.cloud_notm}} console, go to **Schematics** > **Workspaces** and select your instance of the deployable architecture.
    1.  Click **Apply plan**.

        This action resumes the job where it left off. In some cases, when the error was with provisioning a service, this second apply command is successful.

If the issue persists after the second apply, [open a case](/docs/powervs-vpc?topic=powervs-vpc-help-support#support-case-details) in the {{site.data.keyword.cloud_notm}} support center.
{: tsResolve}
