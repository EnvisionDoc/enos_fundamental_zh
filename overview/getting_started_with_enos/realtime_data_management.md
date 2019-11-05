# Unit 4: Managing and Processing Real-time Data

With your devices connected, your data starts to accumulate on EnOS. It could be quite a challenge to manage the vast amount of IoT data. Data Asset Management offering provides services that help you reduce your cost on data storage, lowers development barrier of stream analytics, and increases data access efficiency. 

Before you dive into the offering, you'll want to get yourself familiar with the [key concepts](/docs/data-asset/en/2.0.8/data_asset_concepts) about stream data processing and data storage.

## Real-Time Data Flow

To be able to efficiently manage your data, you'll first need to understand the [Real-time Data Flow](/docs/data-asset/en/2.0.8/learn/data_flow). 

## Configure Storage Policy

Note that the raw data uploaded to EnOS and the stream processing results are NOT stored when you don't configure data storage policy to define which data goes where. 

The storage policy gives you flexibility to determine what data to store, where to store, and how long to store. The design of EnOS data store takes best practices of energy/utility domain into consideration, by allowing you to store time-series data into different buckets according to the data types and provides different APIs for you to access data in different bucket to increase data access efficiency. For more information about data storage policy, see [Configuring TSDB Storage](/docs/data-asset/en/2.0.8/configuring_tsdb_storage).


## Develop Stream Analytics Job

To lower the development barrier of stream analytics, EnOS encapsulates the complexity of the underlying stream processing engine and provides GUI-based data development IDE to help you easily perform stream analytics.

For a deep dive into stream data processing on EnOS, see [Stream Analytics](/docs/data-asset/en/2.0.8/learn/index).


## Get Data through APIs

As mentioned above, EnOS provides a data service API for each TSDB storage type. For more information about these APIs, see [Getting Stored Data with EnOS APIs](/docs/data-asset/en/2.0.8/howto/obtain/getting_stored_data.html) documentation.

## Subscribe to Data

You can also use the Data Subscription service to get your data more efficiently. The Data Subscription Service improves API calling efficiency by actively push data to the subscriber applications when new data arrives. The service allows you to subscribe to the following types of data:

- [Subscribing to Real-time Data](/docs/data-asset/en/2.0.8/quickstart/gettingstarted_subscribe_realtime)
- [Subscribing to Alert Data](/docs/data-asset/en/2.0.8/quickstart/gettingstarted_subscribe_alerts)

## Next Unit

[Batch Processing](batch_processing)

