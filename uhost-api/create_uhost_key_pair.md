# 创建主机密钥对 - CreateUHostKeyPair

## 简介

创建主机密钥对信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUHostKeyPair)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUHostKeyPair`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **KeyPairName** | string | 密钥对名称。 由字母，数字，符号组成，长度为1-63位。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **KeyPair** | [*KeyPair*](#KeyPair) | 密钥信息 |**Yes**|

#### 数据模型


#### KeyPair

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。 |No|
| **KeyPairId** | string | 密钥对ID。 |No|
| **KeyPairName** | string | 密钥对名称。 长度为1\~63个英文或中文字符。 |No|
| **KeyPairFingerPrint** | string | 密钥对指纹。md5(ProjectId\|KeyPairId\|PublicKey) |No|
| **PrivateKeyBody** | string | 密钥对的私钥内容。只有创建接口才会返回。 |No|
| **CreateTime** | int | 密钥对的创建时间，格式为Unix Timestamp。 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUHostKeyPair
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=EmINSQAU
&KeyPairName=IqZZckdR
```

### 响应示例
    
```json
{
  "Action": "CreateUHostKeyPairResponse",
  "KeyPairName": "bRkLZgiA",
  "RetCode": 0
}
```





