# 创建证书 - CreatePathXSSL

## 简介

创建SSL证书，可以把整个 Pem 证书内容传到SSLContent，或者把证书、私钥、CA证书分别传过来






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreatePathXSSL)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreatePathXSSL`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID org-xxx格式。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **SSLName** | string | SSL证书的名字 |**Yes**|
| **SSLType** | string | 所添加的SSL证书类型，目前只支持Pem格式 |No|
| **SSLContent** | string | SSL证书的完整内容，私钥不可使用密码，包括加密证书的私钥、用户证书或CA证书等 |No|
| **UserCert** | string | 用户自签证书内容 |No|
| **PrivateKey** | string | 加密证书的私钥，不可使用密码保护，开启密码保护后，重启服务需要输入密码 |No|
| **CACert** | string | CA颁发证书内容 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **SSLId** | string | SSL证书的Id |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreatePathXSSL
&ProjectId=org-xxx
&SSLName=ssss
&SSLType=Pem
&SSLContent=
&UserCert=---BEGIN----
&PrivateKey=---BEGIN----
&CaCert=
```

### 响应示例
    
```json
{
  "Action": "CreatePathXSSLResponse",
  "RetCode": 0,
  "SSLId": "gssl-xxx"
}
```





