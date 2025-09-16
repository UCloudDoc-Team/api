# 绑定资源到安全组 - AssociateSecGroup

## 简介

绑定资源到安全组

?> 资源和安全组不支持同时传入多个。支持重复绑定，修改绑定优先级也使用该接口。

!> 仅支持绑定同一资源类型的资源


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AssociateSecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AssociateSecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId.N** | string | 资源短 ID，安全组参数和该字段只支持一个批量。支持 string 数组。 |**Yes**|
| **PrioritySecGroup.N.Priority** | int | 绑定优先级。该字段和资源 ID 只支持一个批量。支持 PrioritySecGroup 的 JSON 格式数组。 |**Yes**|
| **PrioritySecGroup.N.SecGroupId** | string | 安全组 ID。该字段和资源 ID 只支持一个批量。支持 PrioritySecGroup 的 JSON 格式数组。 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AssociateSecGroup
&Region=OUsdiWDK
&ProjectId=gWLANZey
&FWId=MwGpFQZd
&ResourceType=IJUSubKV
&ResourceId=fworMOuc
&PrioritySecGroup.N.SecGroupId=wSALafiE
```

### 响应示例
    
```json
{
  "Action": "AssociateSecGroupResponse",
  "RetCode": 0
}
```





