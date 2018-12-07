# FAQs about real-time data processing 

The topic lists frequently asked questions about real-time data processing.


## Q: What is uuid in streaming computing? How to retrieve it?

A: uuid is also known as mdmid, which can be retrieved by getDeviceID() or DevicelCal(). 



## Q: How are the uploaded data points saved in TSDB?

A: There are 2 tables. One saves the uploaded data only. A forced data storage will be triggered if there is no data change within 1 hour. The other saves sampling data by a 1-minute frequency. To query the ingested data within 1 minute, set the interval value of the *Sample_data* parameter.



## Q: Can data in TSDB be deleted?

A: No. Data in TSDB can be covered only, through streaming computing write operation. Data coverage is an unconventional operation, which is not recommended.
