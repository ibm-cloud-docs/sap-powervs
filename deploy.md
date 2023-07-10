---

copyright:
  years: 2023
lastupdated: "2023-07-10"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Deploying the Power Virtual Server for SAP HANA - 'SAP ready PowerVS' Variation
{: #sap-power-automation-deploy}

To deploy the Power Virtual Server for SAP HANA through the {{site.data.keyword.cloud_notm}} console:

1. Go to the {{site.data.keyword.cloud_notm}} catalog and search for 'Power Virtual Server for SAP HANA'. Click the tile.
1. Select the latest version.
1. Select the **SAP ready PowerVS** variation. 
1. Click **Review deployment options**.
    - Select **Add to project** to add this deployment to an {{site.data.keyword.cloud_notm}} project and combine it with other deployments. {{site.data.keyword.cloud_notm}} projects include several more pipeline steps before deployment, including deployment validation, cost calculation, compliance verification, and approval process.
    - Select **Create from the CLI** to get the CLI command. With that command you can trigger the deployment from the CLI.
    - Select **Work with code** to embed the code into other terraform deployments.
    - Select **Deploy with IBM Cloud Schematics** to trigger deployment process directly.

Edit the configuration by entering the **Required input variables**. **Optional input variables** are for advanced configuration and for deeper customization of the provisioned elements. You should know exactly what is the change goal and result by modifying the optional input variables. 
- Input parameters are described in [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/examples/ibm-catalog/deployable-architectures/sap-ready-to-go/README.md){: external}.
- Secure input parameters might be entered directly or might be referenced from an existing {{site.data.keyword.secrets-manager_full_notm}}. For more information, see [Storing arbitrary secrets](/docs/secrets-manager?topic=secrets-manager-arbitrary-secrets).

The deployment typically can take up to 60 minutes but might take longer depending on the performance of {{site.data.keyword.cloud_notm}} components.
{: note}

## Validating the deployment
{: #validate-deployment}

After you provision an instance, verify the success of the deployment by:

- Checking the log files in {{site.data.keyword.bplong_notm}}. There shouldn't be any errors.
- Trying out the access to the bastion host by using a SSH key. Access should be possible. 
- Logging to all created VPC and PowerVS instances. Access should be possible.

## Next steps
{: #sap-powervs-automation-next}

You must put the SAP installation files on the NFS server and perform the software installation according to the SAP documentation.

You can connect to the landscape by using following SSH command:

```sh
ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand=\"ssh -W %h:%p root@\<access_host_floating_ip\>\" root@\<powervs_instance_ip\>
```
