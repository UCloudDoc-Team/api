# 创建SSL证书 - CreateSSL

## 简介

创建SSL证书，可以把整个 Pem 证书内容传过来，或者把证书、私钥、CA证书分别传过来






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateSSL)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateSSL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **SSLName** | string | SSL证书的名字，默认值为空 |**Yes**|
| **SSLType** | string | 所添加的SSL证书类型，目前只支持Pem格式 |No|
| **SSLContent** | string | SSL证书的完整内容，包括用户证书、加密证书的私钥、CA证书 |No|
| **UserCert** | string | 用户的证书 |No|
| **PrivateKey** | string | 加密证书的私钥 |No|
| **CaCert** | string | CA证书 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SSLId** | string | SSL证书的Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateSSL
&Region=cn-bj2
&ProjectId=project-xs13ik
&SSLName=new-ssl
&SSLContent=-----BEGIN&nbspRSA&nbspPRIVATE&nbspKEY-----xxx
```

### 响应示例
    
```json
{
  "Action": "CreateSSLResponse",
  "RetCode": 0,
  "SSLId": "ssl-s1v2e0"
}
```





