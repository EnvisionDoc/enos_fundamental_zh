# 获取CA根证书和证书撤销列表

EnOS提供开放的API接口，用于获取CA根证书和证书撤销列表。

以下API的调用路径是基于`https://<enos_cluster_hostname>`的相对路径，`https://<enos_cluster_hostname>`指的是EnOS云集群实例的域名。当前EnOS有以下公有云集群实例：

- AWS-CN: `https://developer.envisioncn.com`

.. note:: 如果你是私有云用户，该地址为你的私有云部署的域名。

## 获取CA根证书

CA根证书是具有当前CA的公钥的证书。根证书用于检查颁发的证书的有效性。可通过调用以下API接口来获取CA根证书：

```
GET /enos/CA/cacert
```

## 获取证书撤销列表

在证书撤销列表（CRL）中，通过证书序列号来标识被撤销的证书。可通过获取CRL并检查相应的证书序列号是否在CRL中，来确定证书是否被撤销。定期调用以下API接口来获取证书撤销列表：

```
GET /enos/CA/crl
```

.. note:: EnOS X.509证书服务每天早上00:00刷新证书撤销列表。

<!--end-->
