# EnOS Glossaries

## A

### access policy

In IAM, a policy is a collection of access rules. An organization administrator may assign one or more policies to a user.

### access rule

In IAM, an access rule refers to a user's operational permission to an EnOS resource.

### asset

An asset is an instance of a model, which can either be one device or a combination of devices.

### asset tree

An asset tree of an enterprise is formed through hierarchical topology.

### attributes
An attribute is a static description of a device. A static attribute allows the user to customize its name as well as the corresponding identifier. The name is equivalent to a description that allows Chinese input(e.g., longitude).

## B

<h3><a name="batch_computing">batch computing</a></h3>

Batch computing is a way of data processing (usually limited data processing), typically using a file system as its data source. It takes data blocks as processing units, and each computing job receives the data block of a certain size and processes them, and then sends the processed intermediate data downstream. Batch computing jobs are short tasks that are closed after processing a batch of data to which they are assigned.

## C

### custom resources
Custom resources are additional resources an organization needs to purchase or apply for.

## D

### DAG

A directed acyclic graph is a directed graph with no loops. It consists of a finite number of vertices and directed edges, with each directed edge pointing from one vertex to another. And, starting from any of the vertices, you cannot return to the same vertex through these directed edges.

### dashboard

A dashboard is a form of visual presentation of data. In EnOS, reports can be prepared using the reporting tool to drag and drop charts or controls. Multiple types of analytical charts and controls may be included in the reports, and such operations as filtering, screening and associated queries are supported.

### data development

Data development refers to a series of data computing processes (including data generation, collection and storage, data analysis and processing, data extraction and display, etc.) designed based on specific business needs. These computing processes are implemented as one or more scheduling jobs, and processing results are executed and output through a scheduling system.

### data explorer

Data explorer is a tool provided by EnOS for visualizing interactive data analysis, and for querying, analyzing, and visualizing data.

### data integration

Data integration is a tool provided by EnOS for data synchronization.

### data synchronization

Data synchronization is a data transmission process to maintain data consistency between the source and target systems. This process may be accompanied by certain data conversion or cleaning. In EnOS, data synchronization refers to the process of data transmission between EnOS external data sources and storage products in the EnOS cloud.

### dataset

A dataset is a logical table or view that establishes a connection with a source table by simple logical processing based on one or more data source tables. It can be directly associated with the charts in report design. By using datasets, users no longer need to care much about the processing logics of the underlying data source tables.

### device

A device is a physical device that is subordinate to a product. A device has a unique DeviceKey assigned by EnOS. A device can connect directly to the EnOS Cloud.

### device secret

The device secret issued by EnOS is usually paired with Device key and used in conjunction with device key for one-device-one-key authentication.

## E

### event

An event is one occurring when the device is running. An event generally contains notification information that needs to be externally perceived and processed, and may include multiple output parameters. For example, the information completed by a job, or the temperature of a device at the time of failures or alerts, etc. Events can be subscribed and pushed.

## F

### full-load synchronization

Full-load synchronization means that all data of the data source is loaded at one time when data is initialized on the integration side.

## G

### gateway

A gateway is the connector between different networks, which connects a sub device to the EnOS Cloud.

## H

## I

### Identity and Access Management (IAM)

The user identity management and resources access control service that EnOS provides to the clients. With IAM, you can create and manage users and control who has access or operational permissions to what  resources of the organization.

### incremental synchronization

Incremental synchronization means that, upon completion of a certain data synchronization, only the newly added or modified data in a form since the the last synchronization are synchronized. In data integration, the filter " where" is usually used to filter out the content that needs to be incrementally synchronized.

### IoT Hub

The IoT Hub is a cloud access service provided by EnOS for device access. A smart device can establish a secure two-way link with the cloud IoT Hub through the mainstream Internet of Things protocol (MQTT protocol) to quickly build an IoT project or application.

## J

### job

A job (or a scheduling job) is the main object of data development and the main carrier of the data computing processes. It includes computing logics, computing dependencies and scheduling properties. All the data resources related to data computing such as codes, scripts or orders are concatenated in one or more dependent scheduling jobs and executed according to the scheduling attributes, ultimately producing processing results.

## K

## L

## M

### measuring point

A measuring point is generally the operating state of a device. It allows the user to customize the name of a measuring point as well as its identifier. The name is equivalent to a description that allows Chinese input, such as power.

### message queue

A message queue is a container in which messages are saved during transmission. That is, after the message is sent by the sender, it first enters a container for temporary storage. When a certain condition is met, the container is sent to the receiver. This is also called delayed communication of messages.

### meta data

Meta data is the data about data, which is extracted from information resources to describe its characteristics, content, and structure. It is used to organize, describe, retrieve, store, and manage information resources. Meta data managed in EnOS mainly includes the descriptions of databases, data tables, or data content itself.

## N

## O

### offline computing

<p>Please refer to <a href="#batch_computing">batch computing</a>.</p>

### offline data synchronization

Offline data synchronization refers to the periodic transmission of data (such as hourly, daily, weekly, monthly, etc.) into batches from the source system to the target system. Offline data synchronization has a life cycle. An offline synchronization task has a start state and an end state. In this process, data is transmitted from the source to the target in a manner of reading a snapshot.

### one-device-one-key

An authentication method where the device certificates, namely DeviceKey and DeviceSecret, are written in the device when it is burned.

### one-product-one-key

An authentication method where different devices of the same product burn the same firmware (the product certificate is written in the firmware, i.e., ProductKey and ProductSecret). The DeviceKey and DeviceSecret are dynamically obtained from the cloud through the ProductKey when the device is activated.

### organization

In IAM, an organization refers to a collection of users, resources, applications, and services, and is the top-level account management unit. The organization pays for the resources it owns and has full access to all resources under its name.

### organization administrator

In IAM, an organization administrator is a user with full permissions.

## P

### partition

In Hive databases, a partition refers to a logical storage. In querying Hive table data, to avoid wasting time and resources when scanning the entire table for each query, the partition concept is introduced when the table is built, and the data is organized into zones. Data querying may be more effective when the data are grouped in partitions and queries are made by partition.

### product

In EnOS device connection model, a product is the logical combination of a group of devices with shared functionality. A product has a globally unique ProductKey issued by EnOS.

### product secret

The product secret issued by EnOS is usually paired with product key and is used in conjunction with product key for the one-product-one-key authentication.

### publish

Publish is a type of operation permission for Topics, with permission to send messages to Topic queues.

## Q

## R

### real-time computing

<p>Please refer to <a href="#stream_computing">stream computing</a>.</p>

### resource

Resources are the core objects of IAM permission management and are objects that users access. Resources can be divided into system resources and organizational custom resources.

## S

### service

A service is a capability or method by which a device can be called externally. Both its input and output parameters can be configured. Compared with an attribute, a service can perform more complex business logics through instructions, such as performing a specific job.

### service account

A service account is the account that EnOS assigns to an application or service. The service account uniquely identifies an application. The account is required to call EnOS APIs through the service account to access the EnOS resources.

### site

In Tableau, site is the minimum unit managed by Tableau Server. A site has its own URL, users, user groups, and resources (workbooks, data sources) that’s segregated from other sites to achieve multi-tenancy.

<h3><a name="stream_computing">stream computing</a></h3>

Stream computing is a way of processing data, in most cases infinite data. Generally, message queues are used as data sources. It takes data records as processing units, and a record is sent downstream immediately upon completion of a calculation job. Jobs for stream computing are usually long tasks, which run continuously for data reception and processing.

### structured data

Structured data, or row data, is a logically expressed and implemented data from a two-dimensional table structure, typically stored in a database (such as MySQL, Oracle), or in a text file (such as CSV, TXT).

### sub device

A sub device is a physical device that is subordinate to a product. A sub device connects to the EnOS Cloud through a gateway.

### subscribe

Subscribe is a type of operation permission for Topics, with permission to acquire messages from Topic queues.

### system resources

System resources are those assigned to the organization by EnOS by default.

## T

### tag

A tag refers to a shared attribute. Tags are divided into model tags, product tags and device tags.
• Model tags describe the shared information that all model examples under the same model have.
• Product tags describe the shared information that all the devices under one product have.
• A device tag is a unique tag added to a device based on its characteristics.

### task

A task is the smallest executable unit of a job. Different types of tasks are applicable to different business scenarios, where different types of data development can be implemented.

### thing model

A thing model is a functional description of the device in the cloud, including the device attributes, measuring points, services, and events. A thing model is described with a "thing" defined by a description language (TSL or Thing Specification Language), and you can assemble and report the device data in the JSON format.

### time series data

Time series data refers to data generated and recorded in time series. For instance, the data collected and generated by real-time monitoring, inspection and analysis equipment in power/chemical industries.

### topic

In the publish/subscribe model, a topic is the theme of messages. A topic is transmitted through a message queue, and users can publish or subscribe to messages of the corresponding topic to the queue.

### topic type

A topic type refers to a collection of topics of different devices under the same product. One topic type is common to all devices under a ProductKey.

## U

### user

In IAM, a user is an individual who belongs to an organization and can be an organization administrator or a normal user.

### user group

In IAM, a user group is a combination of users who have the same permissions.

### user identity

The user identity is the unique identifier of a user in EnOS. A user is authenticated through the user identity to access the EnOS Console and APIs and authorized to manage and operate the EnOS resources, applications or systems, etc..

## V

## W

### workbook and worksheet

In Tableau, a workbook contains sheets, a sheet can be a worksheet, a dashboard, or a story.

### workflow

A workflow is a directed acyclic graph consisting of one or more tasks that share dependencies or associations with one another. They can work together to complete a more complex data computing process.

### workflow instance

An instance may be generated after the workflow is run in the scheduling system, which represents a snapshot of a workflow at a certain time. An instance contains information about the workflow and the running time, status and the logs of the task.

## X

## Y

## Z
