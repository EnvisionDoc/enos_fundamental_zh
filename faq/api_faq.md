# FAQs about EnOS™ APIs

The topic lists frequently asked questions about calling EnOS APIs.

## Q: What is the amount limit of historical data supported by the *DetailV2* API?

A: The *DetailV2* API retrieves data from TSDB. According to the current logic of TSDB, the *DetailV2* API supports retrieving historical data in the past 3 months.



## Q: If needed, how to retrieve historical data beyond the amount limit (> 3 months)?

A: If there is business requirement, the internal API *DataDownload* supports retrieving historical data beyond the limit of the *DetailV2* API. Contact the support team to enable the *DataDownload* API.



## Q: If needed, how to retrieve time series data beyond the amount limit (> 3 months)?

A: The *Sample_data* API supports this. Contact the support team to create table view under the *rule_engine* library to map new table names. Use Wormhole to export offline data to the new table (with the same rules as TSDB, replacing the metric value in the *wormhole* configuration file from eos_60 to the new table name).



## Q: For organizations with big amount of devices, how to retrieve asset tree?

A: Call the *getObjectStructure* API repeatedly with the *page_size* (less than 3000) and the *exclusive_from* parameters specified  (otherwise an error will be reported), until the value of the response parameter is 0.



## Q: For the DetailV2 API, what is the data ingesting logic of the interval parameter?

A: If no value is specified for the *interval* parameter, second-level data will be retrieved. If a value is specified for the *interval* parameter, the data will be ingested according to the specified frequency. The logic is to ingest the latest data within the past time interval. 



## Q: Why is the size of data returned by the DetailV2 API only10k?

A: The data size is controlled by the *Limit* parameter. The default value is 10k, but the maximum value can be 100k.  It is recommended to specify a small value for each call, while call the API multiple times to retrieve data for long time. 



## Q: What is the range of longitude and latitude and  supported by the InsertObject API?

A: For longitude: -180~180; for latitude: -90~90.



## Q: Why is authentication failed for 3rd party users who call the APIs using authorized APP key and secret?

A: Contact EnOS support team to enable permission for 3rd party users to access the application of the authorized customer.