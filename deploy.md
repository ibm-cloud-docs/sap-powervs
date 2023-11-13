---

copyright:
  years: 2023
lastupdated: "2023-11-10"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Deploying the Power Virtual Server for SAP HANA
{: #sap-power-automation-deploy}

To deploy the Power Virtual Server for SAP HANA through the {{site.data.keyword.cloud_notm}} console:

1. Go to the {{site.data.keyword.cloud_notm}} catalog and search for 'Power Virtual Server for SAP HANA'. Click the tile.
1. Select the latest version.
1. Select the variation.
1. Click **Review deployment options**.
    - Select **Add to project** to add this deployment to an {{site.data.keyword.cloud_notm}} project and combine it with other deployments. {{site.data.keyword.cloud_notm}} projects include several more pipeline steps before deployment, including deployment validation, cost calculation, compliance verification, and approval process.
    - Select **Deploy with IBM Cloud Schematics** to trigger the deployment process directly.

Edit the configuration by entering the **Required input variables**. **Optional input variables** are for advanced configuration and for deeper customization of the provisioned elements. Make sure that you know what you want to achieve by modifying the optional input variables and what the result will be.
- For the **SAP ready PowerVS** variation, the input parameters are described in [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-ready-to-go/README.md){: external}.
- For the **SAP S/4HANA or BW/4HANA** variation, the input parameters are described in [readme file](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-s4hana-bw4hana/README.md){: external}.
- Secure input parameters might be entered directly or might be referenced from an existing {{site.data.keyword.secrets-manager_full_notm}}. For more information, see [Storing arbitrary secrets](/docs/secrets-manager?topic=secrets-manager-arbitrary-secrets).

The deployment typically can take up to 60 minutes for the SAP ready PowerVS variation and up to 2 hours for the SAP S/4HANA or BW/4HANA variation. It might take longer, depending on the performance of {{site.data.keyword.cloud_notm}} components.
{: note}

## Validating the deployment
{: #validate-deployment}

After you provision an instance, verify the success of the deployment by:

- Checking the log files in {{site.data.keyword.bplong_notm}}. There shouldn't be any errors.
- Trying out the access to the bastion host by using an SSH key. Access should be possible.
- Logging to all PowerVS instances. Access should be possible.

You can connect to the landscape by using following SSH command:

- To connect to the HANA instance:

    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_hana_instance_management_ip>
    ```

- To connect to the NetWeaver instance:
    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_netweaver_instance_management_ip>
    ```
