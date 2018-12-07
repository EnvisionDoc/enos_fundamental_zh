# FAQs about batch data processing 

The topic lists frequently asked questions about batch data processing.


## Q: How long will task instance logs be stored?

A: In the data operation module, task instance logs will be stored for 15 days.



## Q: What is the maximum number of lines of the task instance log?

A: The limit of task instance log is 2000 lines. Download the log to view the complete local information.



## Q: When creating a workflow and selecting "Import task config", the error message “workflow config not found” is reported. What are possible reasons?

A: In the imported task configuration package, the *workflow.config* file must be in the root directory of the package. That is, when compressing task configuration files, select all the configuration files and compress them directly. 



## Q: When creating a data integration workflow, and the data source types are FTP, SFTP, and S3, can the column header contain Chinese characters?

A: No, Chinese characters are not allowed in the column header, and the value of the column header must be the same with the number of columns of the file.



## Q: When creating a data integration workflow, and the data source type is S3, how to name the directories and files?

A: When the data source type is S3, the directories and files should start with “s3://”, followed by the file path.



## Q: When creating a workflow, which tasks or task nodes can be referenced as dependency and added to new tasks? 

A: Only periodic tasks or task nodes can be referenced as dependency, and they can be root nodes only.



## Q: When creating a workflow, what does "true" and "false" in relation mean?

A: In a workflow, task nodes can be connected with relation. After connection, task nodes have dependencies at run time. The values "true" and "false" take effect only when the task is cascaded rerun. "true" means that downstream nodes will be executed during rerun, and "false" means that downstream nodes will not be executed. Double-click on the relation to change between "true" and "false". 



## Q: When cloning a workflow, will the downstream dependency relationship of the workflow be copied?

A: No, cloning a workflow will copy its commands, resources, configuration, and upstream dependency relationship, but not downstream dependency relationship. 



## Q: When creating a periodic scheduling workflow, what does "Specific Time" mean in node scheduling configuration? 

A: "Specific Time" means scheduled task running time, which is consistent with the time of cloud servers. For the US and European environment, the time is UTC. For the China environment, the time is UTC+8.



## Q: When creating a workflow, how to configure Crontab in scheduling configuration?

A: A 7-digit Crontab is used in scheduling configuration. In general, Crontab specifies the exact time to trigger an event. For example, c1 (0 1 * * * ? *) defines triggering an event at 1min 0 second of each hour, and c2 (59 59 23 * * ? *) defines triggering an event at 23:59:59 every day. For details, refer to the Crontab web site at http://cron.qqe2.com/.



## Q: Is the timestamp of HDFS data file from device time or platform time? Will delayed records be discarded?  

A: HDFS data are saved with a 1-hour frequency. Data file timestamp is from device time. Delayed upload records will be saved by device timestamp.



## Q: Will files with the same name be overwritten when saving in S3?  

A: Files with the same name will be overwritten by default. If S3 bucket versioning is enabled, a new data version will be generated. 



## Q: In batch processing, is importing site/device master data supported for using master data property to filter device point value? 

A: Yes. Description about "Synchronize master data" can be found through **Data Integration** > **General Library**. Master data can be imported to the Hive library for operations like *Join*.



## Q: Does the master ID (mdmid) in the "Synchronize Master Data" SDK support multiple values? 

A: No. Only one value is supported.





