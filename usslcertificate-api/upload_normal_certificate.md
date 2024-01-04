# 上传托管证书 - UploadNormalCertificate

## 简介

上传托管证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UploadNormalCertificate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateName** | string | 证书名称 |**Yes**|
| **SslPublicKey** | string | 证书公钥base64编码值 |**Yes**|
| **SslPrivateKey** | string | 私钥base64编码值 |**Yes**|
| **SslMD5** | string | 证书签名，将公钥base64和私钥base64拼接起来计算的MD5值 |**Yes**|
| **SslCaKey** | string | 证书链文件内容base64编码值 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CertificateID** | int | 操作的证书Id |No|
| **LongResourceID** | string | 证书的长资源ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UploadNormalCertificate
&SslCaKey=lXUzWbSR
&SslPublicKey=lXUzWbSR
&SslCaKey=lXUzWbSR
&SslMD5=lXUzWbSR
&CertificateName=GoodCertcification

```

### 响应示例
    
```json
{
  "Action": "UploadNormalCertificateResponse",
  "CertificateID": 7,
  "LongResourceID": "FxCzCwyB",
  "RetCode": 0
}
```





