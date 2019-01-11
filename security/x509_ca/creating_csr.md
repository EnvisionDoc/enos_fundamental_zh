## 创建证书签名申请（CSR）

获取EnOS CA颁发的X.509证书，需要为设备或应用创建证书签名申请（CSR）文件。

以下步骤以使用_OpenSSL_为例，介绍创建CSR文件的流程:

1. 生成设备密钥对。

   ```
   openssl genrsa -out <key_name>.key 2048
   ```

   .. note:: 生成密钥对时，必须使用RSA加密算法和2048位密钥长度。`<key_name>`是密钥名称，例如`deviceCert.key`。

2. 为设备或应用创建证书签名申请（CSR）文件。

   ```
   openssl req -new -key <key_name>.key -out <csr_name>.csr -sha256
   ```

   .. note:: `<key_name>.key`文件为步骤1生成的密钥，`<csr_name>` 为CSR文件名，例如`deviceCert.csr`。

   执行命令之后，需要提供以下信息：
   ```
   Country Name (2 letter code) [AU]:
   State or Province Name (full name) []:
   Locality Name (for example, city) []:
   Organization Name (for example, company) []:
   Organizational Unit Name (for example, section) []:
   Common Name (e.g. server FQDN or YOUR name) []:
   Email Address []:
   ```

.. note:: 必须按照CA定义的规范填写：

1. 除 `Email Address` 字段以外，其它字段必填。

2.  `Country Name (C)`，`State or Province Name (ST)`，和 `Organization Name (O)`字段的值必须与CA根证书一致。
