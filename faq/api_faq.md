# EnOS API常见问题

有关EnOS REST API的常见问题如下：

#### 问：接口*getAssetsRawDataByTimeRange*最长可以取多久的历史数据？?

答：接口*getAssetsRawDataByTimeRange*目前数据从TSDB获取，按照当前TSDB的逻辑，只支持取最近3个月的历史数据。



#### 问：如果需要取更长时间(>3个月)的历史数据该怎么办？

答：如果业务需要，可使用大数据平台提供的*DataDownload*接口，可获取超过*getAssetsRawDataByTimeRange*接口限制的历史数据。联系技术支持团队开通*DataDownload*接口权限。



#### 问：对于拥有大量设备的组织，如何正确地获取资产树？

答：调用listAssets接口，并且传入*pageSize*和*pageToken*参数。组织的所有资产信息将通过分页显示。



#### 问：跨Customer授权外部用户访问API，使用的是授权被访问Customer的应用Key和Secret，为什么会认证失败？

答：联系技术支持团队，为访问需求方授权被访问Customer应用的权限。



