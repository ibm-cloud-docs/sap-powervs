---

copyright:
  years: 2023
lastupdated: "2023-12-23"

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


| Certified profile | Volume (GB) | Minimum IOPS | Log-storage tier|
|-------------------|-------------|--------------|-----------------|
| ush1-4x128 |	 4 x 16 GB | 	20,000	| Fixed 5K IOPS |
| ush1-4x256 |	 4 x 32 GB | 	20,000	| Fixed 5K IOPS |	
| ush1-4x384 |	 4 x 48 GB | 	20,000	| Fixed 5K IOPS |		
| ush1-4x512 |	 4 x 64 GB | 	20,000	| Fixed 5K IOPS |		
| ush1-4x768 |	 4 x 96 GB | 	20,000	| Fixed 5K IOPS |
| umh-4x960	 |   4 x 128 GB |	12,800	| Tier 0        |
| umh-6x1440 |	 4 x 128 GB |		12,800	| Tier 0      |	
| mh1-8x1440 |	 4 x 128 GB |		12,800	| Tier 0      |		
| bh1-16x1600|	 4 x 128 GB |		12,800	| Tier 0      |		
| umh-8x1920 |	 4 x 128 GB |		12,800	| Tier 0      |		
| mh1-10x1800|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-20x2000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-10x2400|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-12x2160|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-22x2200|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-12x2880|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-16x2880|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-30x3000|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-60x3000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-16x3840|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-20x3600|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-22x3960|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-35x3500|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-70x3500|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-20x4800|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-25x4500|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-40x4000|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-80x4000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-22x5280|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-30x5400|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-50x5000|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-100x5000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-25x6000|   4 x 128 GB |		12,800	| Tier 0      |
| mh1-35x6300|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-60x6000|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-120x6000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-30x7200|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-40x7200|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-70x7000|	 4 x 128 GB |		12,800	| Tier 0      |
| ch1-140x7000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-35x8400|	 4 x 128 GB |		12,800	| Tier 0      |
| bh1-80x8000|	 4 x 128 GB |		12,800	| Tier 0      |
| umh-40x9600|	 4 x 128 GB |		12,800	| Tier 0      |
| mh1-50x9000| 4 x 128 GB 	|	  12,800	| Tier 0      |
| bh1-100x10000|	 4 x 128 GB| 	12,800	| Tier 0      |
| mh1-60x10800|	 4 x 128 GB 	|	12,800	| Tier 0      |
| umh-50x12000|	 4 x 128 GB 	|	12,800	| Tier 0      |
| mh1-70x12600|	 4 x 128 GB 	|	12,800	| Tier 0      |
| bh1-120x12000|	 4 x 128 GB |	12,800	| Tier 0      |
| umh-60x14400|	 4 x 128 GB 	|	12,800	| Tier 0      |
| mh1-80x14400|	 4 x 128 GB 	|	12,800	| Tier 0      |
| bh1-140x14000|	 4 x 128 GB |	12,800	| Tier 0      |
| mh1-90x16200| 4 x 128 GB 		| 12,800	| Tier 0      |
| mh1-100x18000|	 4 x 128 GB |	12,800	| Tier 0      |
| mh1-125x22500	| 4 x 128 GB 	|	12,800	| Tier 0      |
{: class="simple-tab-table"}
{: tab-group="recommended storage-tier"}
{: caption="Table 1. Recommended storage tier and capacity for log data" caption-side="top"}
{: #log}
{: tab-title="Log"}

| Certified profile | Volume (GB) | Minimum IOPS | Data-storage tier|
|-------------------|-------------|--------------|-----------------|
| ush1-4x128 |	 4 x 77 GB | 	7,500	| Tier 0 |   
| ush1-4x256 |	 4 x 77 GB | 	7,500	| Tier 0 |	
| ush1-4x384 |	 4 x 115 GB | 	7,500	| Tier 0 |		
| ush1-4x512 |	 4 x 154 GB | 	7,500	| Tier 0 |		
| ush1-4x768 |	 4 x 230 GB | 	7,500	| Tier 0 |
| umh-4x960	|    4 x 722 GB	|7,500	|Tier 3|
| umh-6x1440|	4 x 720 GB	  |7,500	|Tier 3|
| mh1-8x1440|	4 x 648 GB	  |7,500	|Tier 3|
| bh1-16x1600|	4 x 660 GB	|7,500	|Tier 3|
| umh-8x1920	|4 x 720 GB	  |7,500	|Tier 3|
| mh1-10x1800	|4 x 648 GB	  |7,500	|Tier 3|
| bh1-20x2000	|4 x 660 GB	  |7,500	|Tier 3|
| umh-10x2400|	4 x 720 GB	|7,500	|Tier 3|
| mh1-12x2160|  4 x 648 GB	|7,500	|Tier 3|
| bh1-22x2200|	4 x 660 GB	|7,500	|Tier 3|
| bh1-25x2500|	4 x 750 GB	|7,500	|Tier 3|
| umh-12x2880|	4 x 864 GB	|7,500	|Tier 3|
| mh1-16x2880|	4 x 864 GB	|7,500	|Tier 3|
| bh1-30x3000|	4 x 900 GB	|7,500	|Tier 3|
| ch1-60x3000|	4 x 900 GB	|7,500	|Tier 3|
| umh-16x3840|	4 x 1152 GB	|7,500	|Tier 3|
| mh1-20x3600|	4 x 1080 GB	|7,500	|Tier 3|
| mh1-22x3960|	4 x 1188 GB	|7,500	|Tier 3|
| bh1-35x3500|	4 x 1050 GB	|7,500	|Tier 3|
| ch1-70x3500|	4 x 1050 GB	|7,500	|Tier 3|
| umh-20x4800|	4 x 1440 GB	|7,500	|Tier 3|
| mh1-25x4500|	4 x 1350 GB	|7,500	|Tier 3|
| bh1-40x4000|	4 x 1200 GB	|7,500	|Tier 3|
| ch1-80x4000|	4 x 1200 GB	|7,500	|Tier 3|
| umh-22x5280|	4 x 1584 GB	|7,500	|Tier 3|
| mh1-30x5400|	4 x 1620 GB	|7,500	|Tier 3|
| bh1-50x5000|	4 x 1500 GB	|7,500	|Tier 3|
| ch1-100x5000|	4 x 1500 GB	|7,500	|Tier 3|
| umh-25x6000|	4 x 1800 GB	|7,500	|Tier 3|
| mh1-35x6300|	4 x 1890 GB	|7,500	|Tier 3|
| bh1-60x6000|	4 x 1800 GB	|7,500	|Tier 3|
| ch1-120x6000|	4 x 1800 GB	|7,500	|Tier 3|
| umh-30x7200|	4 x 2160 GB	|7,500	|Tier 3|
| mh1-40x7200|	4 x 2160 GB	|7,500	|Tier 3|
| bh1-70x7000|	4 x 2100 GB	|7,500	|Tier 3|
| ch1-140x7000|	4 x 2100 GB	|7,500	|Tier 3|
| umh-35x8400|	4 x 2520 GB	|7,500	|Tier 3|
| bh1-80x8000|	4 x 2400 GB	|7,500	|Tier 3|
| umh-40x9600|	4 x 2880 GB	|7,500	|Tier 3|
| mh1-50x9000|	4 x 2700 GB	|7,500	|Tier 3|
| bh1-100x10000|	4 x 3000 GB|	7,500|	Tier 3|
| mh1-60x10800|	4 x 3240 GB	|7,500	|Tier 3|
| umh-50x12000|	4 x 3600 GB	|7,500	|Tier 3|
| mh1-70x12600|	4 x 3780 GB	|7,500	|Tier 3|
| bh1-120x12000|	4 x 3600 GB|	7,500|	Tier 3|
| umh-60x14400|	4 x 4320 GB	|7,500	|Tier 3|
| mh1-80x14400|	4 x 4320 GB	|7,500	|Tier 3|
| bh1-140x14000|	4 x 4200 GB|	7,500|	Tier 3|
| mh1-90x16200|	4 x 4860 GB	|7,500	|Tier 3|
| mh1-100x18000|	4 x 5400 GB|	7,500|	Tier 3|
| mh1-125x22500|	4 x 6750 GB	|7,500	|Tier 3|
{: class="simple-tab-table"}
{: tab-group="recommended storage-tier"}
{: caption="Table 2. Recommended storage tier and capacity for data" caption-side="top"}
{: #data}
{: tab-title="Data"}

| Certified profile | Volume (GB) | Shared-storage tier|
|-------------------|-------------|-----------------|
|ush1-4x128|	1 x 128 GB|	Tier 3|
|ush1-4x256|	1 x 256 GB|	Tier 3|
|ush1-4x384|	1 x 384 GB|	Tier 3|
|ush1-4x512|	1 x 512 GB|	Tier 3|
|ush1-4x768|	1 x 768 GB|	Tier 3|
|umh-4x960|	  1 x 1000 GB|	Tier 3|
|umh-6x1440|	1 x 1000 GB|  Tier 3|
|mh1-8x1440|	1 x 1000 GB|	Tier 3|
|bh1-16x1600|	1 x 1000 GB|	Tier 3|
|umh-8x1920|	1 x 1000 GB|	Tier 3|
|mh1-10x1800|	1 x 1000 GB|	Tier 3|
|bh1-20x2000|	1 x 1000 GB|	Tier 3|
|umh-10x2400|	1 x 1000 GB|	Tier 3|
|mh1-12x2160|	1 x 1000 GB|	Tier 3|
|bh1-22x2200|	1 x 1000 GB|	Tier 3|
|bh1-25x2500|	1 x 1000 GB|	Tier 3|
|umh-12x2880|	1 x 1000 GB|	Tier 3|
|mh1-16x2880|	1 x 1000 GB|	Tier 3|
|bh1-30x3000|	1 x 1000 GB|	Tier 3|
|ch1-60x3000|	1 x 1000 GB|	Tier 3|
|umh-16x3840|	1 x 1000 GB|	Tier 3|
|mh1-20x3600|	1 x 1000 GB|	Tier 3|
|mh1-22x3960|	1 x 1000 GB|	Tier 3|
|bh1-35x3500|	1 x 1000 GB|	Tier 3|
|ch1-70x3500|	1 x 1000 GB|	Tier 3|
|umh-20x4800|	1 x 1000 GB|	Tier 3|
|mh1-25x4500|	1 x 1000 GB|	Tier 3|
|bh1-40x4000|	1 x 1000 GB|	Tier 3|
|ch1-80x4000|	1 x 1000 GB|	Tier 3|
|umh-22x5280|	1 x 1000 GB|	Tier 3|
|mh1-30x5400|	1 x 1000 GB|	Tier 3|
|bh1-50x5000|	1 x 1000 GB|	Tier 3|
|ch1-100x5000|	1 x 1000 GB|	Tier 3|
|umh-25x6000|	1 x 1000 GB|	Tier 3|
|mh1-35x6300|	1 x 1000 GB|	Tier 3|
|bh1-60x6000|	1 x 1000 GB|	Tier 3|
|ch1-120x6000|	1 x 1000 GB|	Tier 3|
|umh-30x7200|	1 x 1000 GB|	Tier 3|
|mh1-40x7200|	1 x 1000 GB|	Tier 3|
|bh1-70x7000|	1 x 1000 GB|	Tier 3|
|ch1-140x7000|	1 x 1000 GB|	Tier 3|
|umh-35x8400|	1 x 1000 GB|	Tier 3|
|bh1-80x8000|	1 x 1000 GB|	Tier 3|
|umh-40x9600|	1 x 1000 GB|	Tier 3|
|mh1-50x9000|	1 x 1000 GB|	Tier 3|
|bh1-100x10000|	1 x 1000 GB|	Tier 3|
|mh1-60x10800|	1 x 1000 GB|	Tier 3|
|umh-50x12000|	1 x 1000 GB|	Tier 3|
|mh1-70x12600|	1 x 1000 GB|	Tier 3|
|bh1-120x12000|	1 x 1000 GB|	Tier 3|
|umh-60x14400|	1 x 1000 GB|	Tier 3|
|mh1-80x14400|	1 x 1000 GB|	Tier 3|
|bh1-140x14000|	1 x 1000 GB|	Tier 3|
|mh1-90x16200|	1 x 1000 GB|	Tier 3|
|mh1-100x18000|	1 x 1000 GB|	Tier 3|
|mh1-125x22500|	1 x 1000 GB|	Tier 3|
{: class="simple-tab-table"}
{: tab-group="recommended storage-tier"}
{: caption="Table 3. Recommended storage tier and capacity for shared data" caption-side="top"}
{: #shared}
{: tab-title="Shared"}
