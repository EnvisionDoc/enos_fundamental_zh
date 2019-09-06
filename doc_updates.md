# 文档更新记录

本文章记录了未包含在发布公告中的文档更新。

有关产品功能及相关文档的更新，参见 [发布公告](releasenotes/index)。

## 2019/09/06发布的文档更新

- 恢复了有关如何在模型中新增事件的描述；增加了新增测点之后，需要及时为测点数据配置存储策略的注解，参见 [创建模型](/docs/device-connection/zh_CN/latest/howto/model/creating_model)。

- 在“将智能设备连接至EnOS Cloud” 入门指引中，增加"步骤4. 为测点数据配置存储策略”，参见 [将智能设备连接至EnOS Cloud](/docs/device-connection/zh_CN/latest/quickstart/gettingstarted_device_connection.html)。

- 在以下操作文档中，更新了示例代码：

  - [连接到EnOS云端](/docs/device-connection/zh_CN/latest/howto/device/develop/java/connect)
  - [通过SSL/TLS连接到EnOS云端](/docs/device-connection/zh_CN/latest/howto/device/develop/java/connect_ssl)
  - [使用配置文件连接到EnOS](/docs/device-connection/zh_CN/latest/howto/device/develop/java/connect_viaprofile)
  - [发送数据到EnOS云端](/docs/device-connection/zh_CN/latest/howto/device/develop/java/post_data_to_cloud)
  - [发送命令到设备](/docs/device-connection/zh_CN/latest/howto/device/develop/java/send_command_to_device)

- 更新了在不使用DTLS加密的情况下使用CoAP协议将设备接入EnOS的文档，不使用DTLS加密的设备通过CoAP协议接入时，不需要拥有AES加密能力，参见以下文档：

  - [CoAP连接通信（非DTLS加密）](/docs/device-connection/zh_CN/latest/reference/coap/coap_non_dtls/connection_non_dtls)
  - [设备上报属性、测点、事件（非DTLS加密）](/docs/device-connection/zh_CN/latest/reference/coap/coap_non_dtls/reporting_data_non_dtls)
  - [云端下发测点设置与服务调用（非DTLS加密）](/docs/device-connection/zh_CN/latest/reference/coap/coap_non_dtls/invoking_service_setting_measure_point_non_dtls)

- 更新了基于MQTT协议连接的文档中的示意图，删除了有关云端集群的描述，参见[基于MQTT协议的连接](/docs/device-connection/zh_CN/latest/learn/message_flow)。

- 更新了资源管理概述相关内容，增加了对可申请资源类型的介绍，参见 [资源管理概述](/docs/enos/zh_CN/latest/resourcemanagement/overview.html)。

  

## 2019/04/10发布的文档更新

- 增加了有关如何在EnOS管理设备生命周期的描述，参见[设备生命周期管理](/docs/device-connection/en/latest/learn/device_lifecycle_management)。
- 增加了有关数据摄取场景及数据格式的描述，参见[数据摄取](/docs/device-connection/en/latest/learn/ingestion/index)。
- 在以下快速指南中增加了示例代码:
  - [将智能设备连接至EnOS Cloud](/docs/device-connection/en/latest/quickstart/gettingstarted_device_connection)
  - [将非智能设备通过edge连接至EnOS Cloud](/docs/device-connection/en/latest/quickstart/gettingstarted_edge_connection)
- 增加了Java SDK的开发者指南，参见[使用Java SDK开发](/docs/device-connection/en/latest/howto/device/develop/java/index)。
- 更新了有关EnOS支持的设备类型的描述，参见[设备连接性](/docs/device-connection/en/latest/learn/connection_scenarios)。
- 更新了如何创建脚本对非EnOS标准数据格式进行解析的信息，参见[创建数据解析脚本](/docs/device-connection/en/latest/howto/device/manage/creating_data_parsing_script)。
- 更新了如何通过EnOS设备协议定义的标准与EnOS Cloud建立连接的信息，参见[使用MQTT协议与EnOS Cloud建立连接](/docs/device-connection/en/latest/reference/mqtt/nonsdk_login)。
