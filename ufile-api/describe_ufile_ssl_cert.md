# 查询SSL证书 - DescribeUFileSSLCert

## 简介

查询指定存储桶所有证书






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUFileSSLCert)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUFileSSLCert`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BucketName** | string | 存储桶名称，全局唯一 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UFileSSLCert*](#UFileSSLCert)] | 证书列表 |No|

#### 数据模型


#### UFileSSLCert

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Domain** | string | 域名 |No|
| **Certificate** | string | SSL证书内容，和域名对应 |No|
| **CertificateKey** | string | SSL证书对应的私钥 |No|
| **CertificateName** | string | SSL证书名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUFileSSLCert
&BucketName=qggNiPKJ
&Domain=LbMuYdGF
```

### 响应示例
    
```json
{
  "Action": "DescribeUFileSSLCertResponse",
  "DataSet": [
    {
      "Certificate": "AdjFfdEC",
      "CertificateKey": "QmKxyiXy",
      "Domain": "PTITmLTh"
    }
  ],
  "RetCode": 0
}
```





