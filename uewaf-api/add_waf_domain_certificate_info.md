# 添加SSL证书 - AddWafDomainCertificateInfo

## 简介

添加SSL证书，支持keyless









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddWafDomainCertificateInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 	<br />项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Domain** | string | 域名 |**Yes**|
| **CertificateName** | string | 证书名称 |**Yes**|
| **SslPublicKey** | string | ssl公钥 |**Yes**|
| **SslMD** | string | 证书MD5校验值，开启keyless只需要计算公钥的md5 |**Yes**|
| **SslKeyless** | string | keyless开关，默认关闭；可选值：开启(on)，关闭(off) |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Id** | int | 添加成功返回的SSL证书ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddWafDomainCertificateInfo
&ProjectId=org-xxx
&Domain=www.test.com
&CertificateName=test
&SslPublicKey=LS0tLS1CRUdJTiBDFURS0tLS0tCk1JSUZyRENDQkpTZ0F3SUJBZ0lRQW
&SslPrivateKey=LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFb3dJQkFBS
&SslMD=617d723ec99fa0a4132a9a54052d4cd6
&SslKeyLess=off

```

### 响应示例
    
```json
{
  "Action": "AddWafDomainCertificateInfoResponse",
  "Id": 6,
  "RetCode": 0
}
```





