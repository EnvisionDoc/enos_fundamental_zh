# EnOS architecture

EnOS provides an integrated, secure and open IoT platform for connecting devices and third party systems to the cloud, mapping the real world unstructured data to the domain digital models, processing data in the real-time and batch manners, and generating reports and business insights.

From a product architecture perspective, EnOS includes

-   EnOS Edge
-   EnOS Cloud
<!--EnOS Open Platform for developers, EnOS Ops Platform for system administrators.>
<!--EnOS Marketplace with applications and solutions, EnOS Management Platform for deployers, configurators and solution architects, and-->

## EnOS Edge

The EnOS Edge is in close contact with assets and provides the ability to securely exchange data with cloud-based services on the EnOS IoT platform such as big data analytics and asset management. The outcomes of the algorithms from big data analytics and the decision rules from asset management can then be sent back to the devices to optimize and maximize performance.

![Edge](media\edge.png)

### Edge Device Hub
EnOS Edge contains an Edge Device Hub. A Device Hub is the container of device drivers.  A Device Driver consists of protocol adapter, typically one for input and one for output,  and device model mapping rule.  A protocol adaptor may be regarded as an interpreter between physical units and data stream. An input adapter serves real-time data acquisition, while output adapter serves device control. Device model mapping rule defines the data transformation method between data stream of a specific device and its logical device model instance.

The EnOS Open Platform provides device protocol SDKs for device vendors and app developer for creating protocol adaptors and device drivers. Certified device protocols pre-bulit in the EnOS device library.

EnOS platform provides the EnOS Management Portal for operators, deployers, configurators and administrators to configure device connectivities in specific projects.

### EnOS IoT Client

The EnOS Edge Connects all devices to EnOS IoT Platform over standard protocols, such as MQTT, and manage all devices as a single global system. The EnOS has local storage and cloud storage. Data is stored and forwarded to the cloud. When network connection is not available, the local storage will hold the data and forward to the cloud when the network becomes available.

### Edge Computing
An important feature of the EnOS Edge is to run the analytics locally. Sometimes, the communications overhead of moving data to the cloud is onerous; transmitting terabytes of data from a remote mine or a ship at sea to the cloud could be prohibitive, and sometimes local autonomy and low-latency response is needed. EnOS allows you to take the human out of the loop and allow the platform to autonomously change the behavior of the connected endpoints or shift data only at convenient times. EnOS enables moving applications from the cloud to the edge, and potentially allowing them to adjust operating variables like fuel flow or direction or temperature.

## EnOS Cloud

Infrastructure layer of EnOS Cloud provides the whole cluster of databases such
as Redis, MySQL, Hbase/HDFS and Common FS. EnOS Cloud applies Ranger for data
security and management and provides time-series data management and offline SQL
data management through Yarn Distributed Resource Manager.

Among these system components, except for TSDB which is developed by Envision,
the rest are leading open source for big data systems.

Envision-developed TSDB component works with Hive to ensure high-responsiveness
and offline storage of large data volume

Ranger ensures the security of data management, and Yarn provides resource
scheduling capability

Other open source components act as the base data storage system, among which
Common FS encapsulates the common file service and shield the data from hosting
environment

*Engine Layer*

The core engine layer of EnOS provides the following engines:

-   Event engine provides event alerts. Event engine obtains device abnormality
    information through event rules such as cross-threshold and combination of
    complex rules.

-   Rule engine functions as an IoT Hub. Rule engine distributes data to
    different engines for further processing based on rules configured.

-   Stream computing and batch job process engines provide core computing
    capability and can sup custom computing and data storage requirements from
    applications.

-   AI and blockchain engine is a dedicated engine for machine learning and
    blockchain application scenarios.

The core engine layer facilitates application development through the service
layer.

*Service Layer*

In the service layer, functions of the service modules are described as follows:

-   Edge management service supports full lifecycle management for edge
    computing devices. The service can monitor and connect device states.

-   Device data access service provides data ingestion and acquisition service
    through API and SDK with bi-directional access to data access points and
    calculation points.

-   Common Data Service provides data services such as weather, electricity
    price, and other common data in the IoT industrial.

-   Application management suite provides application management and debugging
    tools, such as access control and system isolation.

*Device Model and User Access Modules*

The core engine layer and service layer provide external services through user
access and device model modules.

Device model module is a device information database. It provides description
information for device that is connected to EnOS and it allows the connection of
new devices.

User access module provides asset-owner account management and application
account management functions, which provides authentication and authorization
from assets to application.

*EnOS Portal Layer*

EnOS portal is a scalable access interface of EnOS. In addition to the core
computing capabilities of EnOS, the portal can also be scaled to support third
party application and tools.
