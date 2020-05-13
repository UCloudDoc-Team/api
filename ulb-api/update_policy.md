# 更新内容转发规则 - UpdatePolicy

## 简介

更新内容转发规则，包括转发规则后的服务节点





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdatePolicy)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdatePolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 需要添加内容转发策略的负载均衡实例ID |**Yes**|
| **VServerId** | string | 需要添加内容转发策略的VServer实例ID |**Yes**|
| **PolicyId** | string | 转发规则的ID |**Yes**|
| **BackendId.N** | string | 内容转发策略应用的后端资源实例的ID，来源于 AllocateBackend 返回的 BackendId |**Yes**|
| **Match** | string | 内容转发匹配字段 |**Yes**|
| **Type** | string | 内容转发匹配字段的类型 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PolicyId** | string | 转发规则的ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdatePolicy
&Region=cn-bj2
&ProjectId=org-0axxmd
&PolicyId=0a074d02-b7c9-4a5d-9acf-414081f1b85f
&Match=ok
&ULBId=ulb-kix54p
&VServerId=vserver-9b646b
&BackendId.0=backend-67a442
```

### 响应示例
    
```json
{
  "Action": "CreatePolicyResponse",
  "PolicyId": "0a074d02-b7c9-4a5d-9acf-414081f1b85f",
  "RetCode": 0
}
```





