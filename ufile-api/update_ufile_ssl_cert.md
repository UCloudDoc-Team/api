# 更新SSL证书 - UpdateUFileSSLCert

## 简介

更新指定域名证书






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateUFileSSLCert)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateUFileSSLCert`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketName** | string | 存储桶名称，全局唯一 |**Yes**|
| **Domain** | string | 域名 |**Yes**|
| **CertificateName** | string | SSL证书名称 |**Yes**|
| **Certificate** | string | 填写SSL证书文件内容（PEM编码）。 证书文件内容填写格式： 如果您的业务场景仅需确保服务端证书可信，则证书文件需要包含服务器证书（①）和中间证书（②）。如果您的中间证书和服务器证书是两个文件，您可以在证书链配置项填写中间证书内容即可。 |**Yes**|
| **CertificateKey** | string | 填写SSL证书私钥内容（PEM编码）。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateUFileSSLCert
&BucketName=qBzJBwbx
&Domain=DYIHMQtL
&Certificate=nuFuFtqm
&CertificateKey=yMDKnLkT
&CertificateName=zjAasLRx
```

### 响应示例
    
```json
{
  "Action": "UpdateUFileSSLCertResponse",
  "RetCode": 0
}
```





