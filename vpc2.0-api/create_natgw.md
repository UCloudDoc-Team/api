# 创建NAT网关 - CreateNATGW

## 简介

创建NAT网关






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateNATGW)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateNATGW`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目Id。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **NATGWName** | string | NAT网关名称 |**Yes**|
| **SubnetworkIds.N** | string | NAT网关绑定的子网Id |**Yes**|
| **EIPIds.N** | string | NAT网关绑定的EIPId |**Yes**|
| **FirewallId** | string | NAT网关绑定的防火墙Id |**Yes**|
| **VPCId** | string | NAT网关所属的VPC Id。默认为Default VPC Id |No|
| **IfOpen** | int | 白名单开关标记。0表示关闭，1表示开启。默认为0 |No|
| **Tag** | string | 业务组。默认为空 |No|
| **Remark** | string | 备注。默认为空 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NATGWId** | string | 申请到的NATGateWay Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateNATGW
&Region=xxx
&ProjectId=xxx
&NATGWName=yNgsbTKP
&SubnetworkIds.n=YLsLksid
&EIPIds.n=hrjFtZYb
&FirewallId=cuUhZpkK
&VPCId=lunRAEbp
&IfOpen=0
&Tag=xwJQsEdL
&Remark=GREoMkdj
```

### 响应示例
    
```json
{
  "Action": "CreateNATGWResponse",
  "NATGWId": "FPvaAtuP",
  "RetCode": 0
}
```





