# 描述应用型负载均衡监听器 - DescribeListeners

## 简介

描述一个指定的监听器或者一个应用型负载均衡实例下的所有监听器






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeListeners)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeListeners`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ListenerId** | string | 应用型负载均衡监听器的ID。若指定ListenerId，则忽略LoadBalancerId。ListenId和LoadBalancerId必选其一 |No|
| **LoadBalancerId** | string | 应用型负载均衡实例的ID。未指定ListenId，则描述指定的LoadBalancerId下的所有监听器。 |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 数据分页值，默认为100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的负载均衡监听器总数 |No|
| **Listeners** | array[[*Listener*](#Listener)] | 负载均衡监听器信息 |No|

#### 数据模型


#### Listener

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ListenerId** | string | 监听器的ID |No|
| **Name** | string | 监听器的名称 |No|
| **Remark** | string | 监听器的备注信息 |No|
| **ListenerPort** | string | 监听器的监听端口 |No|
| **ListenerProtocol** | string | 监听协议。应用型限定取值： HTTP、HTTPS  |No|
| **Certificates** | array[[*Certificate*](#Certificate)] | （应用型专用）服务器默认证书ID。仅HTTPS监听支持。具体接口详见 Certificate |No|
| **SecurityPolicyId** | string | （应用型专用）安全策略组ID。仅HTTPS监听支持绑定；Default -> 原生策略  |No|
| **IdleTimeout** | int | 连接空闲超时时间。单位：秒 |No|
| **Scheduler** | string | 负载均衡算法。应用型限定取值：Roundrobin -> 轮询;Source -> 源地址； WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数；Backup ->主备模式 |No|
| **StickinessConfig** | array[[*StickinessConfigSet*](#StickinessConfigSet)] | 会话保持相关配置。具体结构详见 StickinessConfigSet |No|
| **HealthCheckConfig** | array[[*HealthCheckConfigSet*](#HealthCheckConfigSet)] | 健康检查相关配置。具体结构详见 HealthCheckConfigSet |No|
| **CompressionEnabled** | boolean | （应用型专用）是否开启数据压缩功能。目前只支持使用gzip对特定文件类型进行压缩 |No|
| **HTTP2Enabled** | boolean | （应用型专用）是否开启HTTP/2特性。仅HTTPS监听支持开启 |No|
| **RedirectEnabled** | boolean | （应用型专用）是否开启HTTP重定向到HTTPS。仅HTTP监听支持开启 |No|
| **RedirectPort** | int | （应用型专用）重定向端口 |No|
| **Targets** | array[[*Target*](#Target)] | 添加的服务节点信息。具体结构详见 Target |No|
| **Rules** | array[[*Rule*](#Rule)] | （应用型专用）转发规则信息 |No|
| **State** | string | listener健康状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康，PartialHealth -> 部分健康，None -> 无节点状态 |No|

#### Certificate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | 证书ID |No|
| **IsDefault** | boolean | 是否为默认证书 |No|

#### StickinessConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | boolean | 是否开启会话保持功能。应用型负载均衡实例基于Cookie实现 |No|
| **Type** | string | （应用型专用）Cookie处理方式。限定枚举值： ServerInsert -> 自动生成KEY；UserDefined -> 用户自定义KEY |No|
| **CookieName** | string | （应用型专用）自定义Cookie。当StickinessType取值"UserDefined"时有效 |No|

#### HealthCheckConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | boolean | 是否开启健康检查功能。暂时不支持关闭。 默认值为：true |No|
| **Type** | string | 健康检查方式。应用型限定取值： Port -> 端口检查；HTTP -> HTTP检查； 默认值：Port |No|
| **Domain** | string | （应用型专用）HTTP检查域名。 当Type为HTTP时，此字段有意义，代表HTTP检查域名 |No|
| **Path** | string | （应用型专用）HTTP检查路径。当Type为HTTP时，此字段有意义，代表HTTP检查路径 |No|

#### Target

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceType** | string | 服务节点的类型。限定枚举值：UHost -> 云主机，UNI -> 虚拟网卡，UPM -> 物理云主机，IP ->  IP类型； 默认值："UHost"； 非IP类型，如果该资源有多个IP，将只能添加主IP； 非IP类型，展示时，会显示相关资源信息，IP类型只展示IP信息。 在相关资源被删除时，非IP类型会把相关资源从lb中剔除，IP类型不保证这个逻辑 |No|
| **ResourceId** | string | 服务节点的资源ID |No|
| **ResourceName** | string | 服务节点的资源名称 |No|
| **VPCId** | string | 服务节点的VPC资源ID |No|
| **SubnetId** | string | 服务节点的子网资源ID |No|
| **ResourceIP** | string | 服务节点的IP |No|
| **Port** | int | 服务节点的端口 |No|
| **Weight** | int | 服务节点的权重。仅在加权轮询算法时有效 |No|
| **Enabled** | boolean | 服务节点是否启用 |No|
| **IsBackup** | boolean | 服务节点是否为备节点 |No|
| **Id** | string | 服务节点的标识ID。为ALB/NLB中使用，与资源自身ID无关，可用于UpdateTargetsAttribute/RemoveTargets |No|
| **State** | string | 服务节点的健康检查状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康<br /> |No|

#### Rule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleId** | string | 转发规则的ID |No|
| **RuleConditions** | array[[*RuleCondition*](#RuleCondition)] | 转发规则匹配条件。具体结构详见 RuleCondition |No|
| **RuleActions** | array[[*RuleAction*](#RuleAction)] | 转发动作。具体规则详见RuleAction |No|
| **IsDefault** | boolean | 是否为默认转发规则 |No|
| **Pass** | boolean | 当转发的服务节点为空时，规则是否忽略 |No|

#### RuleCondition

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 匹配条件类型。限定枚举值：Host，Path |**Yes**|
| **HostConfig** | [*HostConfigSet*](#HostConfigSet) | 域名相关配置。Type为Host时必填。具体结构详见 HostConfigSet |No|
| **PathConfig** | [*PathConfigSet*](#PathConfigSet) | 路径相关配置。Type为Path时必填。具体结构详见 PathConfigSet |No|

#### RuleAction

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 动作类型。限定枚举值：Forward  |**Yes**|
| **ForwardConfig** | [*ForwardConfigSet*](#ForwardConfigSet) | 转发服务节点相关配置。 具体结构详见 ForwardConfigSet  |No|

#### ForwardConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Targets** | array[[*ForwardTargetSet*](#ForwardTargetSet)] | 转发的后端服务节点。限定在监听器的服务节点池里；数组长度可以为0。具体结构详见 ForwardTargetSet |**Yes**|

#### ForwardTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 服务节点的标识ID |**Yes**|
| **Weight** | int | 权重。仅监听器负载均衡算法是加权轮询是有效；取值范围[1-100]，默认值为1 |No|

#### HostConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|
| **MatchMode** | string | 匹配方式。限定枚举值：Regular-正则，Wildcard-泛域名； 默认值：Regular  |No|

#### PathConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeListeners
&Region=cn-bj2
&ProjectId=org-XXXXX
&ListenerId=als-XXXXX
&LoadBalancerId=alb-XXXXX
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeListenersResponse",
  "Listeners": [
    {
      "Certificates": [
        {
          "IsDefault": true,
          "SSLId": "ssl-XXXXXX"
        }
      ],
      "CompressionEnabled": true,
      "HTTP2Enabled": false,
      "HealthCheckConfig": [
        {
          "Enabled": false
        }
      ],
      "IdleTimeout": 60,
      "ListenPort": 80,
      "ListenProtocol": "HTTP",
      "ListenerId": "als-XXXXXX",
      "Name": "als",
      "RedirectEnabled": false,
      "RedirectPort": 7,
      "Remark": "test_als",
      "Rules": [
        {
          "IsDefault": true,
          "Pass": true,
          "RuleActions": [
            {
              "ForwardConfig": {
                "Targets": [
                  {
                    "Id": "ars-XXXXX",
                    "Weight": 1
                  }
                ]
              },
              "Type": "Forward"
            }
          ],
          "RuleConditions": [
            {
              "PathConfig": {
                "Values": [
                  "/"
                ]
              },
              "Type": "Path"
            }
          ],
          "RuleId": "rule-XXXXXX"
        },
        {
          "IsDefault": false,
          "Pass": true,
          "RuleActions": [
            {
              "ForwardConfig": {
                "Targets": [
                  {
                    "Id": "ars-XXXXX",
                    "Weight": 1
                  }
                ]
              },
              "Type": "Forward"
            }
          ],
          "RuleConditions": [
            {
              "PathConfig": {
                "Values": [
                  "/abc"
                ]
              },
              "Type": "Path"
            },
            {
              "HostConfig": {
                "MatchMode": "Regular",
                "Values": [
                  "www.*.com"
                ]
              },
              "Type": "Host"
            }
          ],
          "RuleId": "rule-XXXXXX"
        }
      ],
      "Scheduler": "Roundrobin",
      "SecurityPolicyId": "security-tls12s",
      "StickinessConfig": [
        {
          "CookieName": "test",
          "Enabled": true,
          "Type": "UserDefined"
        }
      ],
      "Targets": [
        {
          "Enabled": true,
          "Id": "ars-XXXXX",
          "IsBackup": false,
          "Port": 80,
          "ResourceIP": "X.X.X.X",
          "ResourceId": "uhost-XXXXXX",
          "ResourceName": "UHost1",
          "ResourceType": "UHost",
          "State": "Unhealthy",
          "SubnetId": "subnet-XXXXX",
          "VPCId": "vnet-XXXXX",
          "Weight": 1
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





