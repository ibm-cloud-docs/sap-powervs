---

copyright:
  years: 2023
lastupdated: "2023-11-10"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Accessing the environment
{: #sap-power-automation-solution-access}

After a successful deployment, {{site.data.keyword.bplong_notm}} provides an output log that lists all IP addresses of the created PowerVS instances. These IP addresses include:
    - An access host IP address that is the entry point to the whole landscape.
    - NFS, DNS, NTP server IP addresses.
    - PowerVS instance IP addresses for SAP HANA (management IP, backup IP, SAP system IP)
    - PowerVS instance IP addresses for SAP NetWeaver (management IP, backup IP, SAP system IP)

SAP solution provisioning as deployable architectures creates a secure and isolated environment. Network communication with the public internet and other landscapes that sit outside of the configured environment is prohibited. Opening the management network channel, for example, for the access with administrator laptop, is the step that must be done manually. In general, there a couple of options for such configuration:

1. Open the VPN connection to the management VPC where access to the host is located.
2. Add an additional IP address to the network access control list of the management VPC where the access host is located. For more information, see the steps in [Access to the environment](/docs/powervs-vpc?topic=powervs-vpc-powervs-automation-solution-access).

After the configuration, you can connect to the landscape by using following SSH command:

To connect to the HANA instance:
```sh
ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_hana_instance_management_ip>
```

To connect to the NetWeaver instance:
```sh
ssh -A -o ServerAliveInterval=60 -o ServerAliveCountMax=600 -o ProxyCommand="ssh -W %h:%p root@<access_host_or_ip>" root@<powervs_netweaver_instance_management_ip>
```

