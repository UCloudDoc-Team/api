# 申请IPv6地址 - AssignIPv6

## 简介

申请IPv6地址






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AssignIPv6)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AssignIPv6`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SubnetworkId** | string | 子网ID |**Yes**|
| **ObjectId** | string | 资源短ID |**Yes**|
| **VPCId** | string | vpc ID |No|
| **InstanceId** | string | 实际资源短ID--pass产品实际ID |No|
| **InstanceType** | int | 与InstanceID对应，实际资源大类ID--pass产品实际类型 |No|
| **Mac** | string | 选填，资源的Mac |No|
| **IPv6Addresses.N** | string | 指定IP分配，与Count互斥 |No|
| **Count** | string | 指定数量分配，与IPv6Addresses互斥 |No|
| **Attribute** | string | IP属性：支持开启公网(Normal)、仅支持内网(Private)，默认Normal |No|
| **Segment** | string | 指定网段分配IP |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **IPv6Addresses** | array[string] | IPv6地址 |**Yes**|
| **OperatorName** | string | IP类型 |**Yes**|
| **IPv6Gateway** | string | IPv6网关 |**Yes**|
| **Mask** | int | 掩码 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AssignIPv6
&Region=cn-zj
&ProjectId=aBrYndgV
&SubnetworkId=ZSalaBuW
&VPCId=sMRyFjkq
&Mac=iwuQSXWZ
&IPv6Addresses.N=zHThxZGW
&Count=igJemmnm
&Attribute=uWNdjGYe
&ObjectId=DmszzDrk
&InstanceId=ecgVlXjf
&InstanceType=7
&Segment=MObSCSqG
```

### 响应示例
    
```json
{
  "Action": "AssignIPv6Response",
  "IPv6Addresses": [
    "UHvTkbtC"
  ],
  "IPv6Gateway": "eHZULCgD",
  "Mask": 2,
  "Message": "pNExjxDU",
  "OperatorName": "ITGAZHLR",
  "RetCode": 0
}
```





