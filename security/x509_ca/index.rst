X.509 证书服务
=================

EnOS提供X.509证书服务，对EnOS Edge和IoT平台之间的所有通信会话强制执行基于X.509证书的双向身份验证。

在密码学中，X.509是定义公钥证书格式的标准，它是用于证明公钥所有权的电子文档。X.509证书由 `RFC5280 <https://tools.ietf.org/html/rfc5280>`__ 标准定义。X.509证书由证书颁发机构(CA)颁发，它是公钥基础设施(PKI)工作组的可信实体。

基于证书的认证与其它身份认证机制相比，有如下优点：

- 非对称密钥，确保敏感密码永远不会脱离设备

- 更强的客户端身份验证

在使用X.509证书服务前，需要了解如下相关概念：

- **Public-key Infrastructure (PKI)**：公钥基础设施，是创建、管理、分发、使用、存储、和撤销数字证书以及管理公钥加密所需的一组角色、策略、和过程。

- **Certification Authority (CA)**：数字证书颁发机构。

- **Certificate signing request (CSR)**：证书签名申请，是证书申请人向证书颁发机构发送的申请X.509证书的消息。

- **Certificate Revocation List (CRL)**：证书撤销列表，是一个带有时间戳的列表，用于维护撤销的CA证书。

EnOS X.509证书服务提供如下功能：

- 获取CA根证书

- 获取证书撤销列表


因此，物联网平台可以获取和撤消X.509证书，以确保设备和云端之间的通信安全。这些功能通过EnOS REST API服务接口提供。

.. toctree::
   :maxdepth: 1

   using_ca_service_api
   secure_communication_iothub
   creating_csr
