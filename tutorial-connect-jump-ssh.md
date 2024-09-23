---

copyright:
  years: 2023, 2024
lastupdated: "2024-09-23"
subcollection: sap-powervs
content-type: tutorial
services: ssh
completion-time: 10mins
keywords:

---

{{site.data.keyword.attribute-definition-list}}

# Connect to Power Virtual Server Instances using floating IP
{: #solution-ssh}
{: toc-content-type="tutorial"}
{: toc-services="ssh"}
{: toc-completion-time="10mins"}

After the deployment has been completed you can connect to the landscape by using ssh proxy command to connect to the private ip of PowerVS instances over floating IP of jump box.
{: shortdesc}

## Before you begin
{: #solution-ssh-prereqs}

1. Make sure you have deployed the [{{site.data.keyword.powerSysFull}} with VPC landing zone](https://cloud.ibm.com/catalog/architecture/deploy-arch-ibm-pvs-inf-2dd486c7-b317-4aaa-907b-42671485ad96-global) deployable architecture landscape by entering a value in the `external_access_ip` field. Only this IP will be allowed to login to the environment as it is allowed in the management-sg group.
1. Review the outputs from the deployable architecture.

## Connect to the landscape
{: #solution-ssh-connect}

1. Make sure you have the right private SSH key.
1. Use the following SSH commands to access the hosts.

- To connect to the HANA instance:

    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_hana_instance_management_ip>
    ```

- To connect to the NetWeaver instance:
    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_netweaver_instance_management_ip>
    ```
