# 将资源从安全组解绑 - DisassociateSecGroup

## 简介

解绑安全组和资源绑定关系

?> 批量使用数组

!> 只传安全组，表示解绑安全组所有的绑定关系；只传资源，表示解绑资源的所有绑定关系；资源和安全组不支持同时传入多个。


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DisassociateSecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DisassociateSecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SecGroupId** | string | 安全组ID数组，为空表示解绑安全组绑定的所以资源，安全组ID和资源ID至少传一个,且只能有一个批量。不支持 .n 格式。Type 为 string 数组。 |No|
| **ResourceId** | string | 资源ID数组，为空表示解绑资源上所有安全组，安全组ID和资源ID至少传一个，且只能有一个批量。不支持 .n 格式。Type 为 string 数组。 |No|
| **Force** | boolean | 是否强制解绑。默认为 false。为 true 表示强制解绑，用于删除资源前的解绑，因为开启安全组特性的资源至少绑定一个安全组，正常情况下是不允许解绑所有安全组。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DisassociateSecGroup
&Region=VGZgsWQX
&ProjectId=akzSYKVG
&ResourceType=ywlgdbdm
&SecGroupId.n=gsnMRBsK
&ResourceId.n=CLJgIEDW
&Force=true
```

### 响应示例
    
```json
{
  "Action": "DisassociateSecGroupResponse",
  "RetCode": 0
}
```





