# 添加应用型负载均衡的后端服务节点 - AddTargets

## 简介

给应用型负载均衡监听器添加后端服务节点






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=AddTargets)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `AddTargets`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **LoadBalancerId** | string | 负载均衡实例的ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **Targets.N.ResourceType** | string | 服务节点的类型。限定枚举值："UHost" / "UNI"/"UPM"/"IP"，默认值："UHost"；非IP类型，如果该资源有多个IP，将只能添加主IP；非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。在相关资源被删除时，非IP类型会把相关资源从lb中剔除，IP类型不保证这个逻辑 |No|
| **Targets.N.ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **Targets.N.VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **Targets.N.SubnetId** | string | 服务节点的子网资源ID。在IP类型时，必传 |No|
| **Targets.N.ResourceIP** | string | 服务节点的IP。在IP类型时，必传 |No|
| **Targets.N.Port** | int | 服务节点的端口。限定取值：[1-65535]，默认值80 |No|
| **Targets.N.Weight** | int | 服务节点的权重。限定取值：[1-100]，默认值1；仅在加权轮询算法时有效<br /> |No|
| **Targets.N.Enabled** | boolean | 服务节点是否启用。默认值true |No|
| **Targets.N.IsBackup** | boolean | 服务节点是否为备节点。默认值false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Targets** | array[[*TargetSet*](#TargetSet)] | 服务节点信息 |No|

#### 数据模型


#### TargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 服务节点的类型。限定枚举值：UHost -> 云主机，UNI -> 虚拟网卡，UPM -> 物理云主机，IP ->  IP类型； 默认值："UHost"； 非IP类型，如果该资源有多个IP，将只能添加主IP； 非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。 在相关资源被删除时，非IP类型会把相关资源从lb中剔除，IP类型不保证这个逻辑  |No|
| **ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **SubnetId** | string | 服务节点的子网资源ID。在IP类型时，必传 |No|
| **ResourceIP** | string | 服务节点的IP。在IP类型时，必传 |No|
| **Port** | int | 服务节点的端口。限定取值：[1-65535]； 默认值：80 |No|
| **Weight** | int | 服务节点的权重。限定取值：[1-100]； 仅在加权轮询算法时有效； 默认值：1 |No|
| **Enabled** | boolean | 服务节点是否启用。 默认值：true |No|
| **IsBackup** | boolean | 服务节点是否为备节点。 默认值：false |No|
| **Id** | string | 服务节点的标识ID。 |No|
| **State** | string | 服务节点的健康检查状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=AddTargets
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=tSIXzLcj
&LoadBalancerId=hWQXJvSD
&ListenerId=dxivFPkq
&Targets.n.ResourceType=rpCZGTgI
&Targets.n.ResourceId=HgfbDNGq
&Targets.n.VPCId=XvDOHmPd
&Targets.n.SubnetId=QQocJvAk
&Targets.n.ResourceIP=pbbYxWoB
&Targets.n.Port=2
&Targets.n.Weight=9
&Targets.n.Enabled=false
&Targets.n.IsBackup=false
&Targets.n.Id=OuqVYQov
```

### 响应示例
    
```json
{
  "Action": "AddTargetsResponse",
  "RetCode": 0,
  "Targets": [
    {
      "Enabled": true,
      "Id": "aaRSmiMG",
      "IsBackup": true,
      "Port": 5,
      "ResourceIP": "HOedmGiS",
      "ResourceId": "hyLxeaCA",
      "ResourceType": "xSewdOoe",
      "State": "UBlOVPSH",
      "SubnetId": "FllAtFNO",
      "VPCId": "BdPHyavQ",
      "Weight": 7
    }
  ]
}
```





