---

copyright:
  years: 2023
lastupdated: "2023-12-21"

keywords:

subcollection: sap-powervs

---

{{site.data.keyword.attribute-definition-list}}

# Sample Storage configuration based on Flexible IOPS
{: #sap-fiops-config}

The storage tier and capacity that is recommended for deployment of SAP S/4HANA on Power Virtual Server is described in this topic. These recommendations are based on the best practices and to meet the minimum performance criteria defined by HCMT.
{: shortdesc}


**Recommendation for SAP HANA DB size 128 GB - 768 GB**
* Use 4 volumes of Fixed 5000 IOPS storage for storing Log files. Log files are usually upto 512 GB and need the high performance
* Use 4 volumes of Tier 0 storage for Data file system 
* Use 1 volume of Tier 3 storage for Shared file system.

**Recommendations for SAP HANA DB size 960 GB - 22.5 TB**
* Use 4 volumes of Tier 0 storage for storing Log files. Log files are usually upto 512 GB and need the high performance
* Use 4 volumes of Tier 3 storage for Data file system 
* Use 1 volume of Tier 3 storage for Shared file system.

Additional Capacity of 150 GB per compute instance for the Operating System + /usr/sap on Tier 3 Storage profile is recommended. For boot volume Tier 3 is sufficent.
{: important}

## Sample storage tier and fiops mapping
{: tier-fiops-map}

The tables below shows the mapping of minimum IOPS and its storage tier mapping based on the different sap profiles.


| Certified profile | Volume (GB) | Minimum IOPS | Log-Storage tier|
|-------------------|-------------|--------------|-----------------|
| ush1-4x128 |	 4 x 16 GB | 	20,000	| Fixed 5K IOPS |
| ush1-4x256 |	 4 x 32 GB | 	20,000	| Fixed 5K IOPS |	
| ush1-4x384 |	 4 x 48 GB | 	20,000	| Fixed 5K IOPS |		
| ush1-4x512 |	 4 x 64 GB | 	20,000	| Fixed 5K IOPS |		
| ush1-4x768 |	 4 x 96 GB | 	20,000	| Fixed 5K IOPS |		

|||||


{: class="simple-tab-table"}
{: tab-group="t-shirt size"}
{: caption="Table 1. T-shirt size and configuration mapping" caption-side="top"}
{: #resize_core_memory-1}
{: tab-title="AIX"}