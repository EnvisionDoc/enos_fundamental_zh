# Unit 3: Connecting and Managing Devices

After logging into EnOS Console, the first thing you start to do is to connect your devices to the cloud. EnOS provides comprehensive connection solutions to help you with device connection and management. 

## Basic Concepts

Before connecting devices to EnOS Cloud, you want to get familiar with the [key concepts](/docs/device-connection/en/latest/device_management_concepts) about device management.


## Connect Your First Device

Devices can be connected to EnOS Cloud directly or through EnOS Edge, depending on the hardware and software capabilities of devices. To understand the types of devices and relevant connection scenarios, see [Device Connectivity](/docs/device-connection/en/latest/learn/connection_scenarios).

To connect a device into EnOS, you'll typically need:
- Cloud side configuration to register the device and obtain device credentials
- Device side development to enable devices to connect and transmit data in a way that complies to EnOS standards

The following quick start guides walk you though the process of device registeration and onboarding to EnOS: 

- [Connecting a Smart Device into EnOS Cloud](/docs/device-connection/en/latest/quickstart/gettingstarted_device_connection)
- [Connecting a Non-Smart Device to EnOS Cloud via Edge](/docs/device-connection/en/latest/quickstart/gettingstarted_edge_connection)

The above guides use Java SDK as an example for device side development. In addition to Java SDK, EnOS also provides open source SDKs for other programing languages. For more information, see [Using the Device SDK](/docs/device-connection/en/latest/howto/device/develop/using_java_sdk).

Don't find the programing language that you want, no worries, we also open our device protocol standards. As long as you send messages to EnOS via specific topics and in our standard message format, your devices can connect to EnOS and starts to transmit data. For more information, see [Not Using SDK](/docs/device-connection/en/latest/howto/device/develop/using_non_sdk).


## Find Out Other Options of Data Ingestion

Now, here we go! If you have successfully connected your device into EnOS by following instructions in the previous section, the real-time device data should already start to transmit from your devices to EnOS Cloud. 

In addition to the typical data ingestion scenario, which deals with real-time data of devices that connect to EnOS. There are many cases where the devices are already connected to a third-party system. And there are cases where devices cannot send data via the stardard EnOS JSON format. To find out more about our connectivity solutions, see [Data Ingestion](/docs/device-connection/en/latest/learn/ingestion/index.html).

## Manage Device Lifecycle on EnOS

EnOS supports end-to-end device lifecycle management, from device registeration to decommission. For a thorough grounding on device management, see [Device Lifecycle Management](/docs/device-connection/en/latest/learn/device_lifecycle_management).


## Next Unit

[Managing and Processing Real-time Data](realtime_data_management) 

