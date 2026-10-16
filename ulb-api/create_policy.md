# 传统型负载均衡创建内容转发策略 - CreatePolicy

## 简介

传统型负载均衡创建VServer内容转发策略

?> 指定转发规则优先级目前只支持针对路径规则生效，暂不支持域名规则之前或域名和路径规则之间调整




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreatePolicy)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreatePolicy`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 需要添加内容转发策略的传统型负载均衡实例ID |**Yes**|
| **VServerId** | string | 需要添加内容转发策略的传统型负载均衡VServer实例ID |**Yes**|
| **BackendId.N** | string | 内容转发策略应用的传统型负载均衡后端资源实例的ID，来源于 AllocateBackend 返回的 BackendId |**Yes**|
| **Match** | string | 内容转发匹配字段 |**Yes**|
| **DomainMatchMode** | string | 内容转发规则中域名的匹配方式，默认与原本一致。枚举值：Regular，正则；Wildcard，泛域名 |No|
| **Type** | string | 内容转发匹配字段的类型 |No|
| **PolicyPriority** | int | 策略优先级，1-9999；只针对路径规则生效 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **PolicyId** | string | 内容转发策略ID |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreatePolicy
&Region=cn-bj2
&ProjectId=project-XXX
&Match=ok
&Type=Domain
&ULBId=ulb-XXXXX
&VServerId=vserver-XXXX
&BackendId.0=backend-XXXX
&PolicyPriority=7
&DomainMatchMode=GxmqumOf
```

### 响应示例
    
```json
{
  "Action": "CreatePolicyResponse",
  "PolicyId": "0a074d02-b7c9-4a5d-9acf-XXXXXXX",
  "RetCode": 0
}
```





