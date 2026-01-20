# 创建ipv6网关 - CreateIpv6Gateway

## 简介

创建ipv6网关






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateIpv6Gateway`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **VPCId** | string | ipv6网关所属的VPCID |**Yes**|
| **Name** | string | IPv6 网关的名称 默认值 Ipv6Gateway |No|
| **Tag** | string | 业务组名称；默认值："Default" |No|
| **Remark** | string |  IPv6 网关的备注信息。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Ipv6GatewayId** | string | ipv6网关ID |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateIpv6Gateway
&Region=rus-mosc
&ProjectId=org-XXXXX
&VPCId=uvnet-XXXXX
&Name= Ipv6Gateway
&Tag= Default
&Remark=Test
```

### 响应示例
    
```json
{
  "Action": "CreateIpv6GatewayResponse",
  "Ipv6GatewayId": "ipv6gw-XXXXX",
  "RetCode": 0
}
```





