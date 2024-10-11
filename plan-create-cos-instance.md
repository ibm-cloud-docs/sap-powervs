---

copyright:
  years: 2023, 2024
lastupdated: "2024-10-11"
subcollection: sap-powervs
content-type: tutorial
services: cloud-object-storage
account-plan: paid
completion-time: 20m
keywords: cos, binaries, s4hana

---

{{site.data.keyword.attribute-definition-list}}

# Create a COS instance with SAP installation files
{: #solution-create-cos-instance}
{: toc-content-type="tutorial"}
{: toc-services="cloud-object-storage"}
{: toc-completion-time="20m"}

[Power Systems Virtual Server for SAP HANA](/catalog/architecture/deploy-arch-ibm-pvs-sap-9aa6135e-75d5-467e-9f4a-ac2a21c069b8-global) requires a COS storage bucket with the SAP HANA installation files.
This tutorial describes how to setup a [Cloud Object Storage (COS) instance](/docs/cloud-object-storage?topic=cloud-object-storage-about-cloud-object-storage) and place the SAP installation files inside. For more information about Cloud object storage, click [here](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage).
{: shortdesc}

## When is this required?
{: #solution-create-cos-instance-when}

The [Power Virtual Server with VPC landing zone](/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) comes with a storage bucket that is meant to be used for the installation files. If you deployed [Power Virtual Server with VPC landing zone](/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) without using a stack solution, check the [Prerequisites](/docs/sap-powervs?topic=sap-powervs-solution-create-cos-instance#solution-create-cos-instance-prerequisites) and skip ahead to [Upload SAP installation binaries](/docs/sap-powervs?topic=sap-powervs-solution-create-cos-instance#solution-create-cos-instance-upload-binaries).
If you're using a stack solution, you need to create your own storage bucket to provide the installation files. In that case, follow every step in this tutorial.

## Prerequisites
{: #solution-create-cos-instance-prerequisites}

### SAP Installation Binaries
{: #solution-create-cos-instance-prereq-binaries}

You need to obtain the HANA and Netweaver installation binaries from SAP. The required installation files depend on the version you're trying to install. To identify which files you need, check out the [PowerVS SAP repo](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/tree/main/solutions/ibm-catalog/sap-s4hana-bw4hana#2-sap-binaries-required-for-installation-and-folder-structure-in-ibm-cloud-object-storage-bucket) and the [sap_hana_install community role](https://github.com/sap-linuxlab/community.sap_install/tree/main/roles/sap_hana_install#sap-hana-software-installation-sar-files).

### IBMCloud CLI Installation and Setup (optional)
{: #solution-create-cos-instance-prereq-ibmcloud-cli}

If you'd like to use the {{site.data.keyword.cloud_notm}} CLI instead of the {{site.data.keyword.cloud_notm}} console in your browser, you need to install and setup the {{site.data.keyword.cloud_notm}} CLI and the object storage plugin. For installation instructions for your operating system, please refer to the [IBMCloud CLI documentation](/docs/cli?topic=cli-getting-started).

Once you finished installing IBMCloud CLI, install the cloud-object-storage plugin:
```sh
ibmcloud plugin install cloud-object-storage
```

Generate an API key to login with the CLI:
1.  Login to the {{site.data.keyword.cloud_notm}} console
1.  Go to **Manage** > **Access IAM**
1.  On the left, click API keys
1.  Click **Create** and follow the instructions. Make sure you store your key somewhere safe.

Login via the IBMCloud CLI:
```sh
ibmcloud login --api-key <your-api-key>
```

### Install AWS CLI to upload the binaries (optional)
{: #solution-create-cos-instance-prereq-aws-cli}

Once the bucket has been created, you'll need a way to upload your installation binaries. You can do so by using the {{site.data.keyword.cloud_notm}} console in your browser without the need to install any additional tools. If you don't want to or can't use the {{site.data.keyword.cloud_notm}} console, this tutorial also describes how to use the AWS CLI. However, it is possible to use many other S3-compatible tools they just aren't covered in this tutorial. For information about uploading objects to COS, you can check out [Upload data](/docs/cloud-object-storage?topic=cloud-object-storage-upload) and [Storing large objects](/docs/cloud-object-storage?topic=cloud-object-storage-large-objects) in the official {{site.data.keyword.cloud_notm}} Object Storage documentation.

The easiest way to install AWS CLI is via `pip install awscli`.

For more information about using the AWS CLI with the {{site.data.keyword.cloud_notm}} Object Storage, check out [Using the AWS CLI](/docs/cloud-object-storage?topic=cloud-object-storage-aws-cli).

## Create a COS Service Instance with a Storage Bucket (optional)
{: #solution-create-cos-instance-creation}
{: step}

Before you can create a storage bucket to store the SAP installation files, you need to create a COS service instance. The service instance is where your storage buckets reside.

1.  Create a Cloud Object Storage service instance

    - By using the {{site.data.keyword.cloud_notm}} console:
        1.  Navigate to **Cloud Object Storage**:
            1.  Click the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Classic Infrastructure** > **Object Storage**
            1.  Click **Create an instance**
        1.  Configure a Cloud Object Storage service instance
            1.  Under **Choose an Infrastructure**, select **IBM Cloud**.
            1.  Select a pricing plan.
            1.  Configure service name, resource group, and tags.
            1.  Click **Create**. It will create a service instance and take you to it.

      Or

    - By using the {{site.data.keyword.cloud_notm}} CLI:

      Make sure you followed the steps in [IBMCloud CLI Setup](/docs/sap-powervs?topic=sap-powervs-solution-create-cos-instance#solution-create-cos-instance-prereq-ibmcloud-cli) and are logged in.
      You will need to select a payment plan. Unless you have a custom plan, typical options are `standard` or `lite`. For more information, refer [here](/docs/cloud-object-storage?topic=cloud-object-storage-provision).

      ```sh
      # select a target resource group for your new service instance
      ibmcloud target -g <resource-group>

      # create the service instance. Make sure to save the ID as it´s needed in the next step
      ibmcloud resource service-instance-create <instance-name> cloud-object-storage <plan> global
      ```

1.  Configure Service Credentials

    You need to create service credentials to enable the deployable architecture to log into the COS instance. You also need them if you want to setup your bucket via the CLI. The deployable architecture requires HMAC credentials, you can find more information [here](/docs/cloud-object-storage?topic=cloud-object-storage-uhc-hmac-credentials-main).

    - By using the {{site.data.keyword.cloud_notm}} console:

    1.  Navigate to your service instance. You can find it by clicking on the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Resource List** > **Storage** > your COS service instance Name
    1.  In the service instance, select the **Service credentials** tab on the top.
    1.  Click **New Credential**.
        1.  Give it a name
        1.  For role, select **Manager**
        1.  For Service ID, select **Create New Service id** and remember what you name it
        1.  Make sure you enable **Include HMAC Credential**

    Or

    - By using the {{site.data.keyword.cloud_notm}} CLI:

    ```sh
    # Create service credentials. Make sure to save the HMAC keys from the output
    ibmcloud resource service-key-create <key-name-without-spaces> Manager --instance-name "<service instance name--use quotes if your instance name has spaces>" --parameters '{"HMAC":true}'
    ```

1.  Create a Storage Bucket:

    - By using the {{site.data.keyword.cloud_notm}} console:

        1.  Navigate to your service instance. The previous step should've taken you directly to your service instance. If it didn't, you can find it by clicking on the **Navigation menu** icon ![Navigation menu icon](../icons/icon_hamburger.svg "Menu") > **Resource List** > **Storage** > your COS service instance Name
        1.  Select **Create a Custom Bucket**.
        1.  Select a **Name** and **Location** *close to your deployment*.
        1.  For the other settings, you can leave the default settings or refer to the [Object Storage Documentation](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage) for more information about the configuration options and [encryption](/docs/cloud-object-storage?topic=cloud-object-storage-tutorial-kp-encrypt-bucket).
        1.  Once done, click **Create Bucket**

      Or

    - By using the {{site.data.keyword.cloud_notm}} CLI:

        For detailed documentation, refer [here](/docs/cli?topic=cli-ic-cos-cli#create-a-new-bucket).
        For a list of endpoints by region, see [here](/docs/cloud-object-storage?topic=cloud-object-storage-endpoints).

        ```sh
        '''Configure cloud object storage plugin.'''

        # select HMAC authentication method
        ibmcloud cos config auth

        # enter HMAC credentials obtained in previous step
        ibmcloud cos config hmac

        # configure the correct endpoint for your region
        ibmcloud cos config endpoint-url --url <endpoint-url>

        '''Create a new bucket'''
        # make sure to pick a region close to your deployment
        ibmcloud cos bucket-create --bucket <bucket-name> --region <region>
        ```

        In case you didn't note down your service id in the previous step, you can obtain it with the following command: `ibmcloud resource service-instance <service-instance-name>` or `ibmcloud resource service-instances --long`
        {: tip}

        You can always list your current cos plugin configuration using `ibmcloud cos config list`
        {: tip}

1.  Configure Bucket Access Policies
    1.  Navigate to your bucket. You can find it in the Buckets tab in your service instance.
    1.  Inside your bucket, go to the Permissions tab and open Access policies.
        1.  For **Policy type**, select **Service ID**
        1.  For **Select a service ID**, select the **service id generated in the previous step**
        1.  For **Role for this bucket**, select **Manager**
        1.  Click **Create access policy**
    1.  You can now obtain and manage this access credential in the IAM console Add how to get there here

## Upload SAP installation binaries
{: #solution-create-cos-instance-upload-binaries}
{: step}

1.  Place the SAP installation binaries in the same folder structure you'd like in your bucket.
1.  Place all your HANA DB files in one directory and all your S/4HANA or BW/4HANA in another one. Do not mix the HANA DB binaries with the S/4HANA or BW/4HANA solution binaries in the same folder, otherwise the ansible playbook execution will fail.
1.  Example folder structure:
    ```text
    S4HANA_2023
    |
    |_HANA_DB
    | |_all IMDB* Files and SAPCAR files (all files similar to listed in point 2 above example file)
    |
    |_S4HANA_2023
      |_all files similar to listed in point 2 above example file
      |maintenance planner stack xml file (optional)
    ```

1.  Upload the files

    - By using the {{site.data.keyword.cloud_notm}} console:

        1.  Navigate to your bucket like described in the previous steps.
        1.  Click **Upload**, a new menu should pop up.
        1.  Select your folder and hit **Upload**.

      Or

    - By using the AWS CLI:
        ```sh
          '''Configure AWS CLI'''
          aws configure
          AWS Access Key ID [None]: <HMAC access_key_id>
          AWS Secret Access Key [None]: <HMAC secret_access_key>
          Default region name [None]: <You can leave this as None>
          Default output format [None]: <You can leave this as None>

          '''Upload your SAP installation binaries'''
          aws --endpoint-url <endpoint> --recursive s3 cp <local directory with binaries> s3://<bucket-name>/<destination-directory>
        ```

You can find the endpoint using the {{site.data.keyword.cloud_notm}} console in your bucket > Configuration > Endpoints. For documentation on endpoints and storage locations, click [here](/docs/cloud-object-storage?topic=cloud-object-storage-endpoints).
{: tip}

Check this [documentation](https://github.com/terraform-ibm-modules/terraform-ibm-powervs-sap/blob/main/solutions/ibm-catalog/sap-s4hana-bw4hana/README.md#2-sap-binaries-required-for-installation-and-folder-structure-in-ibm-cloud-object-storage-bucket) for more information and an example of the binaries required for S/4HANA 2023 and BW/4HANA 2021
{: tip}

During deployment, you have to tell Power Virtual Server for SAP HANA where to find the installation files through the ibmcloud_cos_configuration variable.
{: tip}
