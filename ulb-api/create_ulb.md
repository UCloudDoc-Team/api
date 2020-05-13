# 创建负载均衡 - CreateULB

## 简介

创建负载均衡实例，可以选择内网或者外网



!> OuterMode 与 InnerMode 同时传 Yes 时，以 OuterMode 为准<br />当传了 InnerMode: Yes 之后，需要传一个 SubnetId 来表示用户选择了哪个子网

## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateULB)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateULB`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ULBName** | string | 负载均衡的名字，默认值为“ULB” |No|
| **Tag** | string | 业务组 |No|
| **Remark** | string | 备注 |No|
| **OuterMode** | string | 创建的ULB是否为外网模式，默认即为外网模式 |No|
| **InnerMode** | string | 创建的ULB是否为内网模式 |No|
| **ChargeType** | string | 付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按时付费 |No|
| **VPCId** | string | ULB所在的VPC的ID, 如果不传则使用默认的VPC |No|
| **SubnetId** | string | 内网ULB 所属的子网ID，如果不传则使用默认的子网 |No|
| **BusinessId** | string | ULB 所属的业务组ID，如果不传则使用默认的业务组 |No|
| **FirewallId** | string | 防火墙ID，如果不传，则默认不绑定防火墙 |No|
| **ListenType** | string | ULB 监听器类型，枚举值：RequestProxy，请求代理； PacketsTransmit ，报文转发。默认为RequestProxy |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **ULBId** | string | 负载均衡实例的Id |No|
| **IPv6AddressId** | string | IPv6地址Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateULB
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBName=test
&OuterMode=Yes
&ChargeType=Month
&VPCId=vnet-XXXXX
&SubnetId=subnet-XXXXX
&Tag=test
&FirewallId=wXfLAbgy
```

### 响应示例
    
```json
{
  "Action": "CreateULBResponse",
  "IPv6AddressId": "LTPlnlOm",
  "RetCode": 0,
  "ULBId": "ulb-XXXXX"
}
```





