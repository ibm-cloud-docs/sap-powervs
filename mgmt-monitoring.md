---

copyright:
  years: 2024
lastupdated: "2024-01-30"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Managing and monitoring the deployment
{: #sap-power-automation-solution-monitoring}

For deployment process monitoring, {{site.data.keyword.bplong_notm}} monitoring interfaces are used. The same interface is used to audit and capture all user actions and relevant security events.
{: shortdesc}

For more information, see [Getting started: {{site.data.keyword.bplong_notm}}](/docs/schematics?topic=schematics-getting-started), [Monitoring Schematics services by using IBM Cloud Monitoring](/docs/schematics?topic=schematics-monitoring-instances) and [Auditing events](/docs/schematics?topic=schematics-at_events).

## Infrastructure and landscape management and monitoring after deployment
{: #sap-power-automation-solution-landscape-post-deployment}

For monitoring and management of provisioned resources, VPC and PowerVS interfaces are used. The same interface is used to audit and capture all user actions and relevant security events.

For more information, see [{{site.data.keyword.cloud_notm}} VPC documentation](/docs/vpc?topic=vpc-about-vpc) and [{{site.data.keyword.cloud_notm}} PowerVS documentation](/docs/power-iaas?topic=power-iaas-getting-started).

The following landscape provisioning options are not deployed with this automation and can be added after deployment:
- [IBM Spectrum Protect on IBM Cloud deployment guide](https://www.ibm.com/support/pages/node/6498661){: external}
- [Tutorial - HA configuration for SAP RHEL solutions](/docs/sap?topic=sap-ha-rhel)
- [High-availability configuration for SAP NetWeaver](/docs/sap?topic=sap-netweaver-design-considerations#netweaver-ha)
- [SAP HANA High Availability and Disaster Recovery (HA/DR)](/docs/sap?topic=sap-hana-design-considerations#hana-ha)

## Lifecycle management
{: #sap-power-automation-solution-lifecycle}

Lifecycle management with SAP solution provisioning by using deployable architectures is limited to initial landscape deployments. Landscape update is not supported and must be done manually.

