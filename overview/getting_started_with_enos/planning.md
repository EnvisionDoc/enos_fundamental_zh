# Unit 2: Planning Resource

Congratulations! Now you've logged into the EnOS Console. Before you start your project on EnOS, you will first need to evaluate your volume of devices, data to be uploaded into EnOS, and the computing scale you need. This would help you determine how much computing and storage resource you will need to apply for to support your project.

Based on your business requirement, you can plan for the following resources:

**Stream analytics computing resource**

The specification of the computing resource is defined by the number of data points that can be processed every second. By evaluating your device and measuring point volume, you can decide how much computing resource you will need to apply for.

**TSDB resource**

To store the data ingested from your devices for processing or further analysis, you need to apply for TSDB resource, which includes write resource and storage resource. Currently, only a standard specification can be applied for.

**Batch computing resource**

Computing capability for offline data analytics jobs. Batch computing resources can be requested based on computing unit (CU), with two kinds of computing specifications.

**Data Warehouse Resources**

A subject-oriented and integrated data storage environment for data analysis. Select the appropriate storage size according to actual business requirements (10 ~ 1,000G).

**File Storage HDFS Resources**

HDFS is used for big data analysis and storage scenarios. Select the appropriate storage size according to actual business requirements (10 ~ 1,000G). 

For details about the computing and storage resource specification, see [Resource Specification](/docs/enos/en/2.0.8/resourcemanagement/reference.html).

## Next Unit

[Connecting and Managing Devices](device_connection)

