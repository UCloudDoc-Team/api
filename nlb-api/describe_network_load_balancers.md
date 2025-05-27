# 描述负载均衡实例 - DescribeNetworkLoadBalancers

## 简介

描述负载均衡实例






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNetworkLoadBalancers)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNetworkLoadBalancers`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ShowDetail** | boolean | 是否获取监听器和后端服务节点的详细信息 |No|
| **NLBIds.N** | string | 负载均衡实例的ID，数组 |No|
| **VPCId** | string | 限定所在的VPC |No|
| **SubnetId** | string | 限定所在的子网 |No|
| **Offset** | int | 数据偏移量，默认为0 |No|
| **Limit** | int | 数据分页值，默认为100	 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 满足条件的负载均衡实例总数	 |**Yes**|
| **NLBs** | array[[*NetworkLoadBalancer*](#NetworkLoadBalancer)] | 返回的负载均衡实例列表 |**Yes**|

#### 数据模型


#### NetworkLoadBalancer

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NLBId** | string | 负载均衡实例的ID	 |No|
| **Name** | string | 负载均衡实例的名称 |No|
| **Tag** | string | 负载均衡实例所属的业务组ID |No|
| **Remark** | string | 负载均衡实例的备注信息 |No|
| **IPVersion** | string | 负载均衡实例支持的IP协议版本 |No|
| **VPCId** | string | 负载均衡实例所属的VPC资源ID |No|
| **SubnetId** | string | 负载均衡实例所属的子网资源ID |No|
| **IPInfos** | array[[*IPInfo*](#IPInfo)] | 绑定的IP信息	 |No|
| **ForwardingMode** | string | 负载均衡实例的转发模式 |No|
| **ChargeType** | string | 付费模式 |No|
| **PurchaseValue** | int | 有效期（计费） |No|
| **CreateTime** | int | 负载均衡实例创建时间。格式为 Unix Timestamp	 |No|
| **Listeners** | array[[*Listener*](#Listener)] |  |No|
| **Status** | string | NLB 状态：Normal-正常；Closed-欠费停服；Deleted 已删除 |No|
| **AutoRenewEnabled** | boolean | 是否开启自动续费	 |No|

#### IPInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | string | 唯一标识 ID |No|
| **IP** | string | IP 地址 |No|
| **Type** | int | IP 类型，1（前向 IP）/ 2（后向 IP） |No|
| **IPVersion** | string | IP协议版本，限定枚举值："IPv4" / "IPv6" |No|
| **AddressType** | string | 网络模式，限定枚举值："Internet" / "Intranet" |No|
| **OperatorName** | string | 外网IP的运营商信息，限定枚举值："Telecom" / "Unicom"/"International"/"Bgp"/"Duplet"/"BGPPro"/"China-mobile"/"Anycast" |No|
| **BandwidthType** | int | 带宽类型，限定枚举值：0（普通带宽）/ 1（共享带宽） |No|
| **Bandwidth** | int | 带宽值。单位 M |No|

#### Listener

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ListenerId** | string | 监听器的ID |No|
| **Name** | string | 监听器的名称 |No|
| **Remark** | string | 监听器的备注信息 |No|
| **StartPort** | int | 端口范围的起始端口 |No|
| **EndPort** | int | 端口范围的结束端口 |No|
| **Protocol** | string | 监听协议，限定取值："TCP"/"UDP" |No|
| **Scheduler** | string | 负载均衡算法，限定取值："RoundRobin"/"SourceHash"/"LeastConn"/"WeightLeastConn "/"WeightRoundRobin " |No|
| **StickinessTimeout** | int | 会话保持超时时间。单位：秒，0表示不开启会话保持 |No|
| **ForwardSrcIPMethod** | string | 传递源 IP 方法。限定取值："" / "None" / "Toa"/"ProxyProto"，空字符串和 None 代表关闭。 |No|
| **HealthCheckConfig** | [*HealthCheckConfig*](#HealthCheckConfig) | 健康检查相关配置	 |No|
| **Targets** | array[[*Target*](#Target)] | 服务节点信息 |No|
| **State** | string | listener 健康状态，"Healthy"/"Unhealthy"/"PartialHealth"/"None" |No|

#### HealthCheckConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Enabled** | boolean | 是否开启健康检查功能。 |No|
| **Port** | int | 健康检查探测端口<br />说明：<br />限定取值：[1-65535] |No|
| **Type** | string | 健康检查方式<br />限定取值："Port"/"UDP"/"Ping" /"HTTP"<br />默认值：“Port” |No|
| **Interval** | int | 健康检查间隔时间<br />限定取值：[1-60] 单位秒<br />默认 2s |No|
| **MinSuccess** | int | 健康检查最小成功数<br />限定取值：[1-10] <br />默认 3 |No|
| **MaxFail** | int | 健康检查最大失败数<br />限定取值：[1-10] <br />默认 3 |No|
| **ReqMsg** | string | UDP" 检查模式的请求字符串<br />"HTTP" 检查模式的请求 json 字符串 |No|
| **ResMsg** | string | "UDP" 检查模式的预期响应字符串<br />"HTTP" 检查模式的响应状态码 |No|

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
https://api.ucloud.cn/?Action=DescribeNetworkLoadBalancers
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=XWnVXDaH
&ForwardingMode=fmjZHeSw
&ShowDetail=true
&NLBIds=fCoyYvnX
&VPCId=SNnuSFGY
&SubnetId=bDacFudp
&Offset=3
&Limit=9
```

### 响应示例
    
```json
{
  "Action": "DescribeNetworkLoadBalancersResponse",
  "NLBs": [
    {
      "AutoRenewEnabled": false,
      "ChargeType": "aljeUkow",
      "CreateTime": 9,
      "ForwardingMode": "IpUKAiWW",
      "IPInfos": [
        {
          "Id": "ItnGLdAu"
        }
      ],
      "IPVersion": "GZZZWxKd",
      "Listeners": [
        {
          "ListenerId": "EVzmnRSu"
        }
      ],
      "LoadBalancerId": "ALcsXnSb",
      "Name": "XQhsmXrC",
      "PurchaseValue": 5,
      "Remark": "FkKQmERh",
      "Status": "MUXVamxX",
      "SubnetId": "UAcSxGRB",
      "Tag": "DbTcdEvu",
      "VPCId": "WnqetCLB"
    }
  ],
  "RetCode": 0,
  "TotalCount": 3
}
```





