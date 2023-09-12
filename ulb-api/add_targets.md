# 添加后端服务节点 - AddTargets

## 简介

给监听器添加后端服务节点






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
| **LoadBalancerId** | string | 负载均衡实例ID |**Yes**|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **Targets** | array[[*TargetConfig*](#TargetConfig)] | 要添加的服务节点信息。数组长度至少为1； 不超过20个。具体结构见下方 TargetConfig |**Yes**|

#### 数据模型


#### TargetConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 服务节点的类型。限定枚举值：UHost -> 云主机，UNI -> 虚拟网卡，UPM -> 物理云主机，IP ->  IP类型； 默认值："UHost"； 非IP类型，如果该资源有多个IP，将只能添加主IP； 非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。 在相关资源被删除时，非IP类型会把相关资源从lb中剔除，IP类型不保证这个逻辑 |**Yes**|
| **ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **SubnetId** | string | 服务节点的子网资源ID。在IP类型时，必传 |No|
| **ResourceIP** | string | 服务节点的IP。在IP类型时，必传； |No|
| **Port** | int | 服务节点的端口。限定取值：[1-65535]； 默认值：80 |No|
| **Weight** | int | 服务节点的权重。限定取值：[1-100]； 仅在加权轮询算法时有效； 默认值：1 |No|
| **Enabled** | bool | 服务节点是否启用。 默认值：true |No|
| **IsBackup** | bool | 服务节点是否为备节点。 默认值：false |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Targets** | array[[*TargetSet*](#TargetSet)] | 监听器的ID。具体结构见下方 TargetSet |No|

#### 数据模型


#### TargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 服务节点的类型。限定枚举值：UHost -> 云主机，UNI -> 虚拟网卡，UPM -> 物理云主机，IP ->  IP类型； 默认值："UHost"； 非IP类型，如果该资源有多个IP，将只能添加主IP； 非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。 在相关资源被删除时，非IP类型会把相关资源从lb中剔除，IP类型不保证这个逻辑 |No|
| **ResourceId** | string | 服务节点的资源ID。在非IP类型时，必传 |No|
| **VPCId** | string | 服务节点的VPC资源ID。在IP类型时，必传 |No|
| **SubnetId** | string | 服务节点的子网资源ID。在IP类型时，必传 |No|
| **ResourceIP** | string | 服务节点的IP。在IP类型时，必传 |No|
| **Port** | int | 服务节点的端口。限定取值：[1-65535]； 默认值：80 |No|
| **Weight** | int | 服务节点的权重。限定取值：[1-100]； 仅在加权轮询算法时有效； 默认值：1 |No|
| **Enabled** | bool | 服务节点是否启用。 默认值：true |No|
| **IsBackup** | bool | 服务节点是否为备节点。 默认值：false |No|
| **Id** | string | 服务节点的标识ID。 |No|
| **State** | string | 服务节点的健康检查状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康 |No|




## 示例

### 请求示例
    
```json
curl 'https://api.ucloud.cn' \
--header 'Content-Type: application/json' \
--data '{
    "Action": "AddTargets",
    "Region": "cn-bj2",
    "ProjectId": "project-XXXXX",
    "LoadBalancerId": "alb-XXXXX",
    "ListenerId": "als-XXXXX",
    "Targets": [
        {
            "ResourceType": "IP",
            "VPCId": "uvnet-XXXXX",
            "SubnetId": "subnet-XXXXX",
            "ResourceIP": "X.X.X.X",
            "Port": 80,
            "Enabled": false,
            "IsBackup": true
        },
        {
            "ResourceType": "UHost",
            "ResourceId": "uhost-XXXXX",
            "VPCId": "uvnet-XXXXX",
            "SubnetId": "subnet-XXXXX",
            "Port": 80,
            "Weight": 1,
            "Enabled": false,
            "IsBackup": false
        }
    ]
}'
```

### 响应示例
    
```json
{
    "Action": "AddTargetsResponse",
    "RetCode": 0,
    "Targets": [
        {
            "ResourceType": "IP",
            "ResourceId": "",
            "VPCId": "uvnet-XXXXX",
            "SubnetId": "subnet-XXXXX",
            "ResourceIP": "0.0.0.0",
            "Port": 80,
            "Weight": 1,
            "Enabled": false,
            "IsBackup": true,
            "Id": "ars-XXXXX",
            "State": "Unhealthy"
        },
        {
            "ValueSetMap": null,
            "ResourceType": "UHost",
            "ResourceId": "uhost-XXXXX",
            "VPCId": "uvnet-XXXXX",
            "SubnetId": "subnet-XXXXX",
            "ResourceIP": "",
            "Port": 80,
            "Weight": 1,
            "Enabled": false,
            "IsBackup": false,
            "Id": "ars-XXXXX",
            "State": "Unhealthy"
        }
    ]
}
```





