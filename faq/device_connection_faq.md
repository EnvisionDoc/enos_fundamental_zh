# FAQs about device connection

The topic lists frequently asked questions about device connection and EnOS Edge.

## Q: What is the communication model between the Edge and cloud?

A: EnOS Edge communicates with EnOS Cloud (resource server) using a dynamic HTTPS (port 443) or HTTP (port 80) session. It is configurable to use either HTTPS or HTTP. Over this session, Over this session, EnOS Edge will download necessary resource packages to properly ingest, process, and transfer device telemetry. 



## Q: Why does the resource package need to be updated? What are the requirements and process?

A: The resource package includes asset data (like site information and device information), device model (like base model and child model), protocol jar file, point.csv file, mapping configuration file, and event rule configuration file.  Any modifications to these files (e.g. changes to device attribute) requires resource package updating operation. Usually, these configurations are frequently changes in the implementation phase, and the resource package will become relatively stable in the operation phase (except for some modifications in the maintenance phase). The frequency of resource package update depends on the project requirements.

Resource package update is based on HTTP(s) protocol. Port 80 (HTTP) and port 443 (HTTPs) need to be open in both the cloud and the on-site edge.    

If the resource package is hosted on an FTP server, it can be pushed to users. Users scan the package file and then copy it to an FTP server. The edge will get the package from the FTP server. 



## Q: What are the requirements of remote control commands?

A: Remote control commands are based on TCP protocol. Ports 8043 and 8099 need to be open in the cloud. If a project requires remote control command in the cloud, it will have inbound traffic. 



## Q: What are the requirements of communication debugging and data flow monitoring?

A: Communication debugging and data flow monitoring are based on TCP protocol. Ports 8043 and 8099 need to be open in the cloud.  

The ping and telnet commands in the Configuration Center and the data flow monitoring function need inbound traffic. These functions are optional and designed to enable debugging and problem solving in the implementation and maintenance phases.



## Q: What is the Edge software update frequency?

A: EnOS on-site Edge consists of several modules (execution environment, middleware, applications, and resource packages), which are updated once a month.   



## Q: Does MQTT topic support  wildcard?

A: Yes. For example:

- Multilayer wildcard (#): XXX/level1/level2/# supports receiving all topic messages below level 2.
- Single layer wildcard (+): XXX/level1/level2/+ supports receiving all topic messages below the level under level 2. 