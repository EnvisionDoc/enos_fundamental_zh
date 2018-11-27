# EnOS™ Overview

Envision EnOS™ is an IoT operating system that builds on top of open standards and best design to ensure it operates in an open eco-system. EnOS™ provides comprehensive features and services to cater to different use-case scenarios.

**Extensive connectivity**

Simplified ubiquitous connectivity based on rich protocol library.
- EnOS™ supports direct device connections through the MQTT protocol and connections through the EnOS™ Edge or third-party edge products according to your business needs.
- EnOS™ Edge supports a rich set of industry-standard protocols and some private protocols of mainstream IoT vendors. EnOS™ also provides toolsets to help you develop your own protocol.

For more information, see [Device connection](https://docs.envisioniot.com/docs/device-connection/en/latest/deviceconnection_overview.html).

**Deployment flexibility**

Enterprise-grade software stack with flexible deployment options (public, private, and hybrid cloud).

EnOS™ can operate in private cloud and public cloud hosting environment to enable clients to develop, run and operate their applications without handling the complexity of managing software stacks.

EnOS™ can also be deployed in virtual private cloud (VPC) on public cloud hosting environment and private cloud without dependency on underlying hypervisors. you can also deploy the solution that best suits your requirements for cost, control, configurability, scalability, location and security.


**Domain expertise**

Domain driven data architecture promised by rich experience with smart energy devices and scenarios.

Through extensive domain metadata, EnOS™ supports standardized data acquisition policies, ingestion rules, event handling rules, data retention policies, ODS schema, access control policies and data quality policies cross layer 3 to 5 in the 7-layer reference architecture, as illustrated in Figure 7.
With configurable metadata mapping from the data source to the data target, this process will significantly reduce the effort required for data cleansing and normalization.

**Eco-system**

Seamless integration with native and third-party applications, end-to-end tooling that empowers you to build your own platform.

EnOS™ allows users such as IoT engineers, data scientists, application developers, to perform operations such as managing devices and models, exploring data ingested from devices, configuring event triggering policies, rendering data analysis reports, and managing applications that are developed through the EnOS™ toolsets.

<!--Need to add description about the end user, system admins and application users-->


## Major components

EnOS™ consists of the cloud side and edge side as shown in the following figure.

![EnOS™ architecture](media/architecture.png)

### EnOS™ Cloud

EnOS™ Cloud provides fundamental capabilities of model-based device asset
management, data acquisition, stream data processing, batch data processing,
custom event triggering and time-sequence data query service.

EnOS™ Cloud supports native EnOS™ Edge. If a 3rd party edge is required, EnOS™
Cloud also supports 3rd party edges that are compatible with the EnOS™ device
connection framework.

### EnOS™ Edge

EnOS™ Edge provides capabilities of device data acquisition, device controlling,
data normalization, and model-based real-time computing. The data communication
channels between EnOS™ Edge and EnOS™ Cloud are secured by TLS/SSL protocol with
dedicated X.509 certificate for each edge device and EnOS™ Cloud access point.
