---

copyright:
  years: 2023, 2024
lastupdated: "2024-12-06"
subcollection: sap-powervs
content-type: tutorial
account-plan: paid
completion-time: 30m
keywords: 

---

{{site.data.keyword.attribute-definition-list}}

# Destroy resources deployed by the Deployable Architecture
{: #destroy}
{: toc-content-type="tutorial"}
{: toc-completion-time="30m"}

In this tutorial, you'll learn how to destroy the resources deployed by the [Power Systems Virtual Server for SAP HANA](/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global) Deployable Architecture when you don't need them anymore.  
[Warning]{: tag-red} This will delete all the resources that were created by this deployment and result in total data loss of all data stored on these resources. 
{: shortdesc}

## Prerequisites
{: #destroy-resources-prerequisites}

- You have an existing deployment of [Power Systems Virtual Server for SAP HANA](/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global) that you don't need anymore and want to destroy
- You have backed up all data that you will need in the future that is stored on the resources you're about to destroy
- You deployed using [Projects](/docs/secure-enterprise?topic=secure-enterprise-understanding-projects)

## Destroy the resources
{: #destroy-resources-locate-project}

- By using the {{site.data.keyword.cloud_notm}} console:
    1.  Navigate to the **Configurations** inside your **Project**:
        1.  Click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
        1.  Click on the project name. It will take you to an overview of your project.
        1.  Select the **Configurations** tab.

    1.  Undeploy the resources:
        1.  A project may consist of multiple configurations. Before you proceed, verify you're destroying the correct resources. You can do so by navigating to the **Resources** after clicking on the name of the **configuration**.
        1.  Once you clicked on the name of the configuration that contains the resources you want to destroy, it will show the status of the configuration under its name. The status should show as `Deployed` indicating the resources inside the configuration are active.
        1.  When you're sure you have the right resources, click the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") > **Undeploy**
        1.  It will prompt you to enter the name of your configuration for confirmation.
        1.  The destroy process will begin and it should automatically take you back to the **Configurations** tab inside the **Project**.
            - This process may take a while.
            - The status of your configuration will change to `Undeploying...`.
            - If you ran into any issues during undeployment, please refer to the troubleshooting section in this tutorial
        1.  If you encounter any issues during this process, refer to the [troubleshooting](#destroy-troubleshooting) section
        

    - You can access the logs by clicking on the status `Undeploying...` and clicking on the second line that says `Undeploying resources...`.
    {: tip}

    - Alternatively, you can also follow the process in the related **Schematics workspace**, which you can easily access by clicking on the link under **Workspace** inside your configuration.
    {: tip}

    1.  Cleanup
        Once the status shows ``, you can delete the configuration and if not required anymore also the project.
        1. Delete the **Configuration**:
            1.  In the **Configurations** tab inside the **Project**, select the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") > `Delete`in the same row as your configuration and follow the instructions to complete deletion.
        1.  Once that's done, you can follow these steps to also delete the **Project** in case you don't have other **Configurations** in it:
            1.  Navigate back to all projects. You can do so by either clicking on **Projects** in the top left corner or via the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Projects**.
            1.  Again select the **Options** icon ![Options icon](../icons/action-menu-icon.svg "Options") > `Delete Project`in the same row as your configuration and follow the instructions to complete the process.

## Troubleshooting
{: #destroy-troubleshooting}

If your destroy job failed, check out the following:
1. Examine logs. You can find them either in your project's configuration or in the related Schematics workspace.
1. Determine if there's a resource blocking your destroy process. There is a chance that modifications outside the automation are blocking the resource from getting deleted. Common examples are:
    - additional instances in the power workspace which block subnets from getting deleted
    - locked objects in cloud object storage that block the bucket's deletion.
1. Try to clean up the resource that's blocking the destroy process from finishing.
1. Re-trigger the destroy process inside projects
1. Should this not work, you may have to clean up the remaining resources manually. You can use the resource list and filter for resource group, prefix, and tags to easier locate the related resources (hint: you can find the prefix you defined during deployment inside your project configuration).
1. Should manual deletion of resources fail, navigate to the support center and open a ticket
