# 活动日志架构

本文介绍了活动日志的架构及具体参数。


## 日志示例<samplecode>

```
{
  "userIdentity": {
    "userId": "u15420087818641",
    "userName": "db001",
    "type": "userAccount",
    "accessKey": null,
    "sessionContext": {
      "id": "IAM_S_e6huGLv6FMUW7KCNYZ28zuPML7Uwzg8d",
      "creationDate": "2018-11-20 10:04:20",
      "mfaAuthenticated": false
    }
  },
  "organizationId": "o15420087814661",
  "sourceIpAddress": "172.20.17.248",
  "eventTime": "2018-11-20 10:04:20",
  "eventId": "signInSelectOrganization15427082605511",
  "eventName": "signInSelectOrganization",
  "eventType": "consoleAction",
  "eventVersion": "V1.0",
  "resources": [
    {consoleSignIn
      "resourceId": "u15420087818641",
      "resourceName": "db001",
      "resourceType": "user"
    },
    {
      "resourceId": "o15420087814661",
      "resourceName": "db001",
      "resourceType": "organization"
    }
  ],
  "serviceName": "IAM-Service",
  "requestId": null,
  "requestParameters": "{\"sessionId\":\"IAM_S_e6huGLv6FMUW7KCNYZ28zuPML7Uwzg8d\",\"workingOrganizationId\":\"o15420087814661\",\"organizationId\":\"o15420087814661\"}",
  "apiVersion": null,
  "errorCode": null,
  "errorMsg": null
}
```

## 参数描述<description>

- **UserIdentity**：执行本次活动的用户的信息。
  + **type**：该用户的账号类型。 <!--Currently only has account type _userAccount_.-->
  + **userId**：该用户的唯一识别码。
  + **userName**：该用户的用户名。
  + **sessionContext**：此事件的会话信息。用户通过控制台执行操作时，会触发session创建并记录该信息。一个会话包含下列信息：
    - **id**：该会话的唯一识别码。
    - **creationDate**：该会话创建的日期和事件。
    - **mfAuthentication**：用户登录时是否进行了多因子认证。
- **sourceIpAddress**：发送API请求的源IP地址。如果API请求是由用户通过EnOS控制台操作触发，则记录用户浏览器端的IP地址。
- **eventTime**：API请求的时间戳（UTC格式）。
- **eventId**：事件的唯一识别码，由审计服务生成。
- **eventName**：事件的行为。具体参考[事件列表](#event_types)。
- **eventType**：事件所属的类型。例如, 用户登录(ConsoleSignIn), 用户登出(ConsoleSignOut)和控制台或API操作(ApiCall).
- **eventVersion**：事件格式的版本。
- **resource**：本次活动中被操作的资源。
  + **resourceId**：资源的唯一识别码。
  + **resourceName**：资源的名称。
  + **resourceType**：资源类型，如策略(Policy)，用户(User)和用户组(Usergroup)等。
- **serviceName**：API所属的服务模块，如IAM。
- **requestId**：API请求的唯一识别码。
- **requestParameters**：API请求的输入参数。
- **apiVersion**：调用API的版本。
- **responseElements**：返回的信息。例如：状态变更成功(success)或失败(failed)。
- **errorCode**：返回的错误码。
- **errorMessage**： 返回的错误信息。

## 事件列表<eventlist>

可能被返回的事件列表如下：

.. list-table::
   :header-rows: 1

   * - 事件
     - 描述
   * - consoleSignIn
     - 用户从EnOS控制台登录
   * - consoleSignOut
     - 用户从EnOS控制台登出
   * - signInSelectOrganization
     - 用户登录时选择组织
   * - createUser
     - 创建用户
   * - deleteUser
     - 删除用户
   * - resetUserPassword
     - 管理员重置用户密码
   * - modifyUserPassword
     - 用户修改密码
   * - retrieveUserPassword
     - 用户找回密码
   * - setUserAccountStatus
     - 管理员设置用户账号状态，包括启用(enable)和停用(disable)
   * - addExternalUser
     - 导入外部用户
   * - removeExternalUser
     - 移除外部用户
   * - createGroup
     - 创建用户组
   * - deleteGroup
     - 删除用户组
   * - addUserToGroup
     - 添加用户至用户组
   * - removeUserFromGroup
     - 将用户从用户组移出
   * - createPolicy
     - 创建策略
   * - deletePolicy
     - 删除策略
   * - appendResource
     - 将服务添加到策略
   * - revokeResource
     - 从策略中移除服务
   * - grantPolicy
     - 将策略授权于用户或用户组
   * - removePolicy
     - 从用户或用户组中移除策略

<!--end-->
