---

copyright:
  years: 2024
lastupdated: "2024-01-30"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Accessing the environment
{: #sap-power-automation-solution-access}

After a successful deployment, {{site.data.keyword.bplong_notm}} provides an output log that lists all IP addresses of the created PowerVS instances. These IP addresses include the following resources:

    - An access host IP address that is the entry point to the whole landscape.
    - NFS, DNS, NTP server IP addresses.
    - PowerVS instance IP addresses for SAP HANA (management IP, backup IP, SAP system IP)
    - PowerVS instance IP addresses for SAP NetWeaver (management IP, backup IP, SAP system IP)

SAP solution provisioning as deployable architectures creates a secure and isolated environment. Network communication with the public internet and other landscapes that sit outside of the configured environment is prohibited, for example, the management network channel for the access with the administrator laptop. A couple of options are available for this configuration:

- Open the VPN connection to the management VPC where access to the host is located.
- Add another IP address to the network access control list of the management VPC where the access host is located.

For more information, see the steps in [Access to the environment](/docs/powervs-vpc?topic=powervs-vpc-powervs-automation-solution-access).

After you configure access, you can connect to the landscape by using following SSH command:

- To connect to the HANA instance:

    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_hana_instance_management_ip>
    ```

- To connect to the NetWeaver instance:

    ```sh
    ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_netweaver_instance_management_ip>
    ```
