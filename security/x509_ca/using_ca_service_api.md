# 获取CA根证书和证书撤销列表

EnOS提供开放的API接口，用于获取CA根证书和证书撤销列表。

获取CA根证书和证书撤销列表的API接口，可通过以下EnOS网关地址：

- AWS-CN: `https://developer.envisioncn.com`
- DECADA: `https://portal-decada1.envisioniot.com`

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
