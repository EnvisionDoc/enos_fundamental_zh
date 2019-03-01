# 使用X.509证书最佳实践

安全在物联网系统中至关重要。EnOS推行以下安全方案来保护边缘网关设备和EnOS物联网平台之间的连接：

- 边缘网关设备和EnOS物联网平台之间的通信必须使用基于证书的双向认证。
- 支持RSA加密算法验证签名，并强制要求2048位长。
- EnOS云端的资源被隔离保存，并且API访问权限由IAM控制，详见[IAM简介](https://www.envisioniot.com/docs/iam/zh_CN/latest/iam_overview.html)。

## 配置阶段

下图说明了基于X.509证书的Edge设备和IoT平台之间的安全通信过程：

.. image:: ../media/certificate_service_secure_communication_01.png
   

### 1. IoT平台获取X.509证书

1a. IoT平台在本地创建私钥对和证书签名申请，通过X.509证书服务API接口获取X.509证书。

1b. EnOS CA颁发X.509证书，并将证书发回到IoT平台。

1c. IoT平台接收并保存X.509证书。

.. image:: ../media/certificate_service_secure_communication_02.png
   

### 2. Edge获取X.509证书

2a. 设备接入器通过提供Edge设备的信息，如产品ID、产品秘密、序列号、和许可证等，在IoT平台创建设备。

2b. IoT平台验证Edge设备的身份信息之后，在平台创建设备实例，并返回设备的全局唯一标识符（GUID）和设备密钥。

2c. Edge设备接收IoT平台返回的信息，创建私钥对和证书签名申请，调用API接口激活设备并获取X.509证书。

2d. IoT平台接收Edge设备的请求，完成身份验证之后，激活设备并将设备证书签名申请转发到EnOS CA。

2e. EnOS CA接收到设备的证书签名申请之后，颁发证书并将证书返回到IoT平台。

2f. IoT平台接收到颁发的X.509证书之后，将证书与设备ID绑定，并将证书发送到设备。

2g. Edge设备接收颁发的X.509证书，并将证书安全地保存到本地存储库中。

## 通信阶段

下图说明了基于证书的身份验证过程和证书撤销过程：

.. image:: ../media/certificate_service_secure_communication_03.png
   

### 3. Edge设备与IoT平台之间通过基于证书的双向认证进行通信

3a. Edge设备验证IoT平台的证书。

3b. IoT平台验证Edge设备的证书。

当通过步骤3a和3b的TLS握手成功之后，Edge设备与IoT平台之间建立起TLS连接。

3c. Edge设备通过建立的TLS连接，将设备遥测数据通过MQTT协议上传到IoT平台。

3d. IoT平台通过建立的TLS连接，将配置信息和控制信号通过MQTT协议下发到Edge设备。

.. image:: ../media/certificate_service_secure_communication_04.png
   

## 撤销证书

在特定情况下，设备接入器需要撤销Edge设备的X.509证书。

### 4. IoT平台撤销Edge设备的X.509证书

4a. IoT平台通过调用证书撤销接口，传入证书序列号，申请撤销X.509证书。

4b. EnOS CA接收IoT平台的申请，验证身份，撤销证书，并且更新证书证书撤销列表。

## 边缘设备安全最佳实践

在基于证书的安全连接过程中，考虑采用以下最佳实践来办证Edge设备的安全：

- 为Edge设备创建的私钥，并将其保密在诸如TPM的存储器中。
- 与IoT平台的通信过程中使用TLS 1.2协议，并验证服务器证书是否有效。
- 每台Edge设备必须具有单独的公钥/私钥对。
- 用于在IoT平台上进行身份验证的密钥对不应用于其他目的，或通过其他协议进行通信。
- Edge设备重置时，密钥必须被撤销。
- 当Edge设备运行于某种操作系统上时，确保操作系统通过某些安全机制（例如，防火墙）受到保护。
- 确保CA根证书和证书撤销列表可被更新。
- 确保Edge设备的时钟不可被篡改。
