# 功能改进及行为变更

该部分介绍了在本次发布中的功能改进及行为变更。


## API

有关API的更新详情，登录EnOS控制台，从导航菜单中点击 **EnOS API > 更新说明**。

### 告警服务


.. list-table::
   :widths: auto
   :header-rows: 1

   * - API名称
     - 更新内容
   * - Create Alert Rule
     - 请求参数（Body）中新增参数 ``triggeringDelayTimer``， 用于设定延后告警触发时间。
   * - Search Active Alert
     - 响应参数 ``ActiveAlert`` 结构体中的参数 ``value`` 支持记录 ``triggeringDelayTimer`` 开始计时时测点的值。
   * - Search Alert Rule
     - 响应参数 ``AlertRule`` 结构体中新增参数 ``triggeringDelayTimer``，表示告警被延后触发的时间。
   * - Search History Alert
     - 功能变更为查询**最近三个月内**的历史告警。
        响应参数 ``HistoryAlert`` 结构体中的参数 ``value`` 支持记录 ``triggeringDelayTimer`` 开始计时时测点的值。
   * - Update Alert Rule
     - 请求参数（Body） ``alertRule`` 结构体中新增参数 ``triggeringDelayTimer``， 用于设定延后告警触发时间。


### TSDB数据服务

.. list-table::
   :widths: auto
   :header-rows: 1

   * - API名称
     - 更新内容
   * - Get Asset AI Raw Data
     - 在请求参数（URI）中，新增 ``withQuality`` 参数，用于获取数据质量位。
   * - Get Asset Generic Data 
     - 在请求参数（URI）中，新增 ``withQuality`` 参数，用于获取数据质量位。
   * - Get Asset Raw Data by Time Range
     - 在请求参数（URI）中，新增 ``withQuality`` 参数，用于获取数据质量位。



## EnOS Edge

.. csv-table::
   :header: "服务/功能模块", "变更前", "变更后", "影响分析"
   :widths: auto

   "Edge管理", "用户在需要转发EnOS Edge数据到第三方系统时，无法交付完整的点表", "支持通过导出整表功能，将完整的点表导出", "无"
   "模板配置", "用户必须手动配置采集点到模型测点的映射", "支持通过自动映射功能完成采集点到模型测点的映射", "无"
   "模板配置", "设备采集点上传EnOS Cloud时，其时间戳为系统时间戳", "支持自带时间戳的采集点上传到云端后使用自己的OEM时间戳", "无"
   "模板配置", "设备采集点都必须上送至EnOS Cloud", "支持设置不上送某个模型测点相关的采集点数据", "无"
   "通信规约", "用户无法在创建规约时指定版本号", "支持按照规定的命名格式指定版本号", "无"




## 设备管理 

.. csv-table::
   :header: "服务/功能模块", "变更前", "变更后", "影响分析"
   :widths: auto

   "模型管理、产品管理、设备管理、资产树", "模型、产品、设备、资产树、资产的名称对特殊符号仅支持连字符（ - ）、下划线（ _ )、英文句号（.）和英文冒号（:）", "模型、产品、设备、资产树、资产的名称增加对正斜杠（/）、星号（*）、加号（+）、井号（#）、空格（ ）的支持", "无"
   "设备管理", "用户只能通过模型、设备名称、Device Key、Asset ID来搜索设备", "支持用户通过产品搜索并批量导出设备", "无"
   "设备管理", "用户必须逐个定义设备模拟器数据样本，逐个启停、删除设备模拟器", "支持为同类模型的设备批量定义数据样本，批量启停、删除模拟器", "无"
   "设备管理、资产管理", "设备、资产、资产树信息分开存储。使用API搜索设备和资产信息，搜索的数据量大时，体验不佳", "将设备信息（Product key、Device key、设备状态等）、资产（Asset ID、根据模型定义的属性等）以及资产所在资产树信息存储在单一源。并提升了`Search Device`、`Search Asset Node`API的搜索性能，在搜索结果数据量较大时，用户体验更好。", "无"
   "告警服务", "用户必须逐条创建告警级别、类型、内容、规则", "支持通过编辑模板并上传的方式批量创建告警级别、类型、内容、规则，单次最多导入10000条", "无"
   "告警服务", "用户必须通过告警内容、规则的编号来搜索内容、规则", "新增支持通过模型搜索告警内容、规则，并在搜索结果中选择规则批量导出", "无"