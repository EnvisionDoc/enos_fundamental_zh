### Edge Device Hub

The device hub is the container of _device drivers_. The device driver consists of the _protocol adapters_, typically one for input and one for output, and the _device model mapping rule_. A protocol adaptor is the interpreter between physical units and data stream. The input adapter serves real-time data acquisition, while the output adapter serves device control. The device model mapping rule defines the data transformation method between the data stream of a specific device and its logical device model instance.

EnOS provides device protocol SDKs for device manufacturers and application developers to create protocol adaptors and device drivers. Certified device protocols are pre-bulit in the EnOS device library.

### EnOS IoT Client

The EnOS Edge Connects all devices to EnOS Cloud as an IoT Client over standard protocols, such as MQTT, and manage all devices as a single global system. The EnOS has local storage and cloud storage. Data is stored and forwarded to the cloud. When network connection is not available, the local storage will hold the data and forward to the cloud when the network becomes available.

### Edge Computing

An important feature of the EnOS Edge is to run analytics locally. Edge computing can meet requirements of the following scenarios:
- You want to reduce the communications overhead of moving data to the cloud.
- The amount of data generated is large. Transmitting terabytes of data from a remote mine or a ship at sea to the cloud could be prohibitive.
- Local autonomy and low-latency response is needed.

EnOS allows you to take the human out of the loop and allow the platform to autonomously change the behavior of the connected endpoints and shift data only at convenient times. EnOS enables moving applications from the cloud to the edge, and potentially allowing them to adjust operating variables such as fuel flow and temperature.
