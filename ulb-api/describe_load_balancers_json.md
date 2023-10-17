# 描述负载均衡实例 - DescribeLoadBalancers

## 简介

描述特定条件下的负载均衡实例或者全部的负载均衡实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeLoadBalancers)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeLoadBalancers`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Type** | string | 负载均衡实例的类型。限定枚举值：Application -> 应用型，Network -> 网络型； 默认值："Application" |No|
| **ShowDetail** | bool | 是否获取监听器和后端服务节点的详细信息。默认值：false |No|
| **LoadBalancerIds** | array[string] | 负载均衡实例的ID。必须是同一类型的实例，若指定了实例ID，将忽略除Type外的其他过滤条件 |No|
| **VPCId** | string | 限定所在的VPC |No|
| **SubnetId** | string | 限定所在的子网 |No|
| **Offset** | int | 数据偏移量。默认为0 |No|
| **Limit** | int | 数据分页值。默认为100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **LoadBalancers** | array[[*LoadBalancer*](#LoadBalancer)] | 监听器的ID。具体结构见下方 LoadBalancer |No|

#### 数据模型


#### LoadBalancer

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LoadBalancerId** | string | 负载均衡实例的ID |No|
| **Type** | string | 负载均衡实例的类型。限定枚举值：Application -> 应用型，Network -> 网络型 |No|
| **Name** | string | 负载均衡实例的名称 |No|
| **Tag** | string | 负载均衡实例所属的业务组ID |No|
| **Remark** | string | 负载均衡实例的备注信息 |No|
| **IPVersion** | string | 负载均衡实例支持的IP协议版本 |No|
| **VPCId** | string | 负载均衡实例所属的VPC资源ID |**Yes**|
| **SubnetId** | string | 负载均衡实例所属的子网资源ID。负载均衡实例的内网VIP和SNAT场景的源IP限定在该子网内；指定子网不影响添加后端服务节点时的范围，依旧是整个VPC下支持的资源 |**Yes**|
| **IPInfos** | array[[*IPInfo*](#IPInfo)] | 绑定的IP信息。具体结构详见 IPInfo |No|
| **SnatIPs** | array[string] | 应用型实例的代理IP或网络型FULLNAT模式下snat所用的IP |No|
| **Firewall** | [*FirewallInfo*](#FirewallInfo) | 防火墙信息。具体结构详见FirewallInfo |No|
| **AccessLogConfig** | [*AccessLogConfigSet*](#AccessLogConfigSet) | （应用型专用）访问日志相关配置。具体结构详见 AccessLogConfigSet |No|
| **ChargeType** | string | 付费模式。限定枚举：Year -> 年，Month -> 月，Dynamic -> 时 |No|
| **PurchaseValue** | int | 计费有效期。格式为Unix Timestamp |No|
| **CreateTime** | int | 负载均衡实例创建时间。格式为Unix Timestamp |No|
| **Listeners** | array[[*Listener*](#Listener)] | 监听器信息。当ShowDetail为false时，不显示。具体结构详见 Listener |No|
| **Status** | string | lb状态。Normal -> 正常；Arrears -> 停服 |No|
| **AutoRenewEnabled** | bool | 是否开启自动续费 |No|

#### 数据模型


#### IPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **IP** | string | IP地址 |No|
| **Id** | string | 唯一标识ID |No|
| **IPVersion** | string | IP协议版本 |No|
| **AddressType** | string | 网络模式。 限定枚举值：Internet -> 互联网，Intranet -> 内联网 |No|
| **OperatorName** | string | 外网IP的运营商信息。枚举值为：Telecom -> 电信，Unicom -> 联通，International -> 国际IP，Bgp -> BGP，Duplet -> 双线（电信+联通双线路），BGPPro -> 精品BGP，China-mobile -> 中国移动，Anycast -> AnycastEIP |No|
| **BandwidthType** | int | 带宽类型。限定枚举值：1 -> 共享带宽，0 -> 普通带宽类型 |No|
| **Bandwidth** | int | 带宽值。单位M |No|

#### FirewallInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FirewallId** | string | 防火墙ID |No|
| **FirewallName** | string | 防火墙名称 |No|

#### AccessLogConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | bool | 应用型专用）是否开启访问日志记录功能 |No|
| **US3BucketName** | string | （应用型专用）用于存储访问日志的bucket |No|
| **US3TokenId** | string | （应用型专用）上传访问日志到bucket所需的token |No|

#### Listener

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ListenerId** | string | 监听器的ID |**Yes**|
| **Name** | string | 监听器的名称 |No|
| **Remark** | string | 监听器的备注信息 |No|
| **ListenerPort** | int | 监听器的监听端口 |No|
| **ListenerProtocol** | string | 监听协议。应用型限定取值： HTTP、HTTPS |No|
| **Certificates** | array[[*Certificate*](#Certificate)] | （应用型专用）服务器默认证书ID。仅HTTPS监听支持。具体接口详见 Certificate |No|
| **SecurityPolicyId** | string | （应用型专用）安全策略组ID。仅HTTPS监听支持绑定；Default -> 原生策略 |No|
| **IdleTimeout** | int | 连接空闲超时时间。单位：秒 |No|
| **Scheduler** | string | 负载均衡算法。应用型限定取值：Roundrobin -> 轮询;Source -> 源地址； WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数；Backup ->主备模式 |No|
| **StickinessConfig** | [*StickinessConfigSet*](#StickinessConfigSet) | 会话保持相关配置。具体结构详见 StickinessConfigSet |No|
| **HealthCheckConfig** | [*HealthCheckConfigSet*](#HealthCheckConfigSet) | 健康检查相关配置。具体结构详见 HealthCheckConfigSet |No|
| **CompressionEnabled** | bool | 应用型专用）是否开启数据压缩功能。目前只支持使用gzip对特定文件类型进行压缩 |No|
| **HTTP2Enabled** | bool | （应用型专用）是否开启HTTP/2特性。仅HTTPS监听支持开启 |No|
| **RedirectEnabled** | bool | （应用型专用）是否开启HTTP重定向到HTTPS。仅HTTP监听支持开启 |No|
| **RedirectPort** | int | （应用型专用）重定向端口 |No|
| **Targets** | array[[*Target*](#Target)] | 添加的服务节点信息。具体结构详见 Target |No|
| **Rules** | array[[*Rule*](#Rule)] | （应用型专用）转发规则信息 |No|
| **State** | string | listener健康状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康，PartialHealth -> 部分健康，None -> 无节点状态 |No|

#### Certificate

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SSLId** | string | 证书ID |No|
| **IsDefault** | bool | 是否为默认证书 |No|

#### StickinessConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | bool | 是否开启会话保持功能。应用型负载均衡实例基于Cookie实现 |No|
| **Type** | string | （应用型专用）Cookie处理方式。限定枚举值： ServerInsert -> 自动生成KEY；UserDefined -> 用户自定义KEY |No|
| **CookieName** | string | （应用型专用）自定义Cookie。当Type取值"UserDefined"时有效 |No|

#### HealthCheckConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | bool | 是否开启健康检查功能。暂时不支持关闭。 |No|
| **Type** | string | 健康检查方式。应用型限定取值： Port -> 端口检查；HTTP -> HTTP检查； 不传则默认不修改 |No|
| **Domain** | string | （应用型专用）HTTP检查域名。 当Type为HTTP时，此字段有意义，代表HTTP检查域名； 不传则默认不修改 |No|
| **Path** | string | （应用型专用）HTTP检查路径。当Type为HTTP时，此字段有意义，代表HTTP检查路径； 不传则默认不修改 |No|

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
| **Enabled** | bool | 服务节点是否启用 |No|
| **IsBackup** | bool | 服务节点是否为备节点 |No|
| **Id** | string | 服务节点的标识ID。为ALB/NLB中使用，与资源自身ID无关，可用于UpdateTargetsAttribute/RemoveTargets |No|
| **State** | string | 服务节点的健康检查状态。限定枚举值：Healthy -> 健康，Unhealthy -> 不健康 |No|

#### Rule
| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleId** | string | 转发规则的ID |No|
| **RuleConditions** | array[[*RuleCondition*](#RuleCondition)] | 转发规则匹配条件。具体结构详见 RuleCondition |No|
| **RuleActions** | array[[*RuleAction*](#RuleCondition)] | 转发动作。具体规则详见RuleAction |No|
| **IsDefault** | bool | 是否为默认转发规则 |No|
| **Pass** | bool | 当转发的服务节点为空时，规则是否忽略 |No|

#### RuleCondition

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 匹配条件类型。限定枚举值：Host，Path |**Yes**|
| **HostConfig** | [*HostConfigSet*](#HostConfigSet) | 域名相关配置。Type为Host时必填 |No|
| **PathConfig** | [*PathConfigSet*](#PathConfigSet) | 路径相关配置。Type为Path时必填 |No|

#### HostConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MatchMode** | string | 匹配方式。限定枚举值：Regular-正则，Wildcard-泛域名； 默认值：Regular |No|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|

#### PathConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Values** | array[string] | 取值。暂时只支持数组长度为1； 取值需符合相关匹配方式的条件 |**Yes**|

#### RuleAction

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 动作类型。限定枚举值：Forward |**Yes**|
| **ForwardConfig** | [*ForwardConfigSet*](#ForwardConfigSet) | 转发服务节点相关配置。 具体结构详见 ForwardConfigSet |No|

#### ForwardConfigSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Targets** | array[[*ForwardTargetSet*](#ForwardTargetSet)] | 转发的后端服务节点。限定在监听器的服务节点池里；数组长度可以为0。具体结构详见 ForwardTargetSet |**Yes**|

#### ForwardTargetSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 服务节点的标识ID |**Yes**|
| **Weight** | int | 权重。仅监听器负载均衡算法是加权轮询是有效；取值范围[1-100]，默认值为1 |No|




## 示例

### 请求示例
    
```json
curl 'https://api.ucloud.cn' \
--header 'Content-Type: application/json' \
--data '{
    "Action": "DescribeLoadBalancers",
    "Region": "cn-bj2",
    "ProjectId": "project-XXXXX",
    "Type": "Application",
    "ShowDetail": false,
    "LoadBalancerId": [
        "alb-XXXXX"
    ],
    "VPCId": "uvnet-XXXXX",
    "SubnetId": "subnet-XXXXX",
    "Offset": 0,
    "Limit": 100,
}'
```

### 响应示例
    
```json
{
    "Action": "DescribeLoadBalancersResponse",
    "RetCode": 0,
    "TotalCount": 1,
    "LoadBalancers": [
        {
            "AccessLogConfig": {
                "Enabled": false
            },
            "AutoRenewEnabled": true,
            "ChargeType": "Month",
            "CreateTime": 1000000000,
            "Firewall": {
                "FirewallId": "firewall-XXXXX",
                "FirewallName": "test"
            },
            "IPInfos": [
                {
                    "AddressType": "Internet",
                    "Bandwidth": 1,
                    "BandwidthType": 0,
                    "IP": "X.X.X.X",
                    "IPVersion": "IPv4",
                    "Id": "eip-XXXXX",
                    "OperatorName": "Bgp"
                },
                {
                    "AddressType": "Intranet",
                    "IP": "10.1.1.1",
                    "IPId": "lbip-XXXXX",
                    "IPVersion": "IPv4"
                }
            ],
            "IPVersion": "IPv4",
            "LoadBalancerId": "alb-XXXXX",
            "Name": "ALB-1",
            "PurchaseValue": 1000000000,
            "Remark": "test",
            "SnatIPs": [
                "10.1.1.2"
            ],
            "Status": "Normal",
            "SubnetId": "subnet-XXXXX",
            "Tag": "Test",
            "Type": "Application",
            "VPCId": "uvnet-XXXXX"
        }
    ]
}
```





