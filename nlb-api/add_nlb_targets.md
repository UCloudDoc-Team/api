# 添加后端服务节点 - AddNLBTargets

## 简介

给监听器添加后端服务节点






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddNLBTargets)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddNLBTargets`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NLBId** | string | 负载均衡实例的ID。 |**Yes**|
| **ListenerId** | string | 监听器的ID。 |**Yes**|
| **Targets.N.ResourceType** | string | 服务节点的类型。限定枚举值："UHost" / "UNI"/"UPM"/"IP"，默认值："UHost"；非IP类型，如果该资源有多个IP，将只能添加主IP；非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。 |No|
| **Targets.N.ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **Targets.N.ResourceName** | string | 服务节点的资源名称<br /> |No|
| **Targets.N.VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **Targets.N.SubnetId** | string | 服务节点的子网资源ID。<br /> |No|
| **Targets.N.ResourceIP** | string | 服务节点的IP。在IP类型时，必传 |No|
| **Targets.N.Port** | int | 服务节点的端口，限定取值：[1-65535] |No|
| **Targets.N.Weight** | int | 服务节点的权重。限定取值：[1-100]，默认值1；仅在加权轮询、加权最小连接数算法时有效 |No|
| **Targets.N.Enabled** | boolean | 服务节点是否启用 |No|
| **Targets.N.Region** | string | 服务节点所在地域 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Targets** | array[[*Target*](#Target)] |  |**Yes**|

#### 数据模型


#### Target

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 服务节点所在地域 |No|
| **ResourceType** | string | 服务节点的类型 |No|
| **ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **ResourceName** | string | 服务节点的资源名称 |No|
| **VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **SubnetId** | string | 服务节点的子网资源ID。在IP类型时，必传 |No|
| **ResourceIP** | string | 服务节点的IP。在IP类型时，必传 |No|
| **Port** | int | 服务节点的端口 |No|
| **Weight** | int | 服务节点的权重。支持更新 |No|
| **Enabled** | boolean | 服务节点是否开启 |No|
| **Id** | string | 服务节点的标识 ID<br />说明：<br />添加服务节点的时候无需传<br />更新服务节点属性时必传 |No|
| **State** | string | 服务节点的健康检查状态<br />说明：<br />描述服务节点信息时显示<br />限定枚举值："Healthy"/"Unhealthy" |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddNLBTargets
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=uxOCbBUU
&NLBId=UnhYzuYf
&ListenerId=IShmtmhn
&Targets=pGKemNMo
&Targets.n.ResourceId=lTXwhUoW
&Targets.n.ResourceName=RSMxnGlA
&Targets.n.VPCId=IvTAXOkH
&Targets.n.SubnetId=XyBZrEjL
&Targets.n.ResourceIP=zsAVZQWG
&Targets.n.Port=thIdtrsC
&Targets.n.Weight=gHrJImio
&Targets.n.Enabled=true
&Targets.n.Region=wHRTiRhi
```

### 响应示例
    
```json
{
  "Action": "AddNLBTargetsResponse",
  "RetCode": 0,
  "Targets": [
    {
      "Id": "LMVtHghN",
      "Port": 1,
      "ResourceIP": "kQHmnadz",
      "ResourceId": "aEEHbHSB",
      "ResourceName": "LwwGwBev",
      "ResourceType": "RwgIAUHV",
      "State": "kvujNDos",
      "SubnetId": "PuxrjzqU",
      "VPCId": "WZFfrwoe",
      "Weight": 7
    }
  ]
}
```





