# 下载上传或购买的证书 - DownloadCertificate

## 简介

下载购买或上传的证书









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DownloadCertificate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CertificateID** | int | 证书编号 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **CertificateUrl** | string | 证书的下载路径 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DownloadCertificate
&CertificateID=1
```

### 响应示例
    
```json
{
  "Action": "DownloadCertificateResponse",
  "CertCA": {
    "FileData": "-----BEGIN CERTIFICATE----------END CERTIFICATE-----",
    "FileName": "CertificateCA.pem"
  },
  "Certificate": {
    "FileData": "-----BEGIN CERTIFICATE----------END CERTIFICATE-----",
    "FileName": "Certificate.pem"
  },
  "CsrOnline": 0,
  "RetCode": 0
}
```





