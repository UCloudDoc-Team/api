# 创建VServer - CreateVServer

## 简介

创建VServer实例，定义监听的协议和端口以及负载均衡算法





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateVServer)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateVServer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ULBId** | string | 负载均衡实例ID |**Yes**|
| **VServerName** | string | VServer实例名称，默认为"VServer" |No|
| **ListenType** | string | 监听器类型，枚举值，RequestProxy ，请求代理；PacketsTransmit ，报文转发。默认为RequestProxy |No|
| **Protocol** | string | VServer实例的协议，请求代理模式下有 HTTP、HTTPS、TCP，报文转发下有 TCP，UDP。默认为“HTTP" |No|
| **FrontendPort** | int | VServer后端端口，取值范围[1-65535]；默认值为80 |No|
| **Method** | string | VServer负载均衡模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）; WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数。<br />ConsistentHash，SourcePort，ConsistentHashPort 只在报文转发中使用；Leastconn只在请求代理中使用；Roundrobin、Source和WeightRoundrobin在请求代理和报文转发中使用。<br />默认为："Roundrobin" |No|
| **PersistenceType** | string | VServer会话保持方式，默认关闭会话保持。枚举值：None -> 关闭；ServerInsert -> 自动生成KEY；UserDefined -> 用户自定义KEY。 |No|
| **PersistenceInfo** | string | 根据PersistenceType确认； None和ServerInsert： 此字段无意义； UserDefined：此字段传入自定义会话保持String |No|
| **ClientTimeout** | int | ListenType为RequestProxy时表示空闲连接的回收时间，单位：秒，取值范围：时(0，86400]，默认值为60；ListenType为PacketsTransmit时表示连接保持的时间，单位：秒，取值范围：[60，900]，0 表示禁用连接保持 |No|
| **MonitorType** | string | 健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；Ping -> Ping探测，<br />请求代理型默认值为Port，其中TCP协议仅支持Port，其他协议支持Port和Path;<br />报文转发型TCP协议仅支持Port，UDP协议支持Ping和Port，默认值为Ping |No|
| **Domain** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查域名 |No|
| **Path** | string | 根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查路径 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **VServerId** | string | VServer实例的Id |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateVServer
&Region=cn-bj2
&ProjectId=project-XXXXX
&Action=CreateVServer
&ULBId=ulb-XXXXX
&ListenType=RequestProxy
&PersistenceType=None
&PersistenceInfo=hsdhs
&Protocol=TCP
&VServerName=testvserver1
&Method=Source
&FrontendPort=80
&ClientTimeout=180
&MonitorType=EAWmpFKo
&Domain=HbTPGDtS
&Path=ScoEPSuy
```

### 响应示例
    
```json
{
  "Action": "CreateVServerResponse",
  "RetCode": 0,
  "VServerId": "vserver-XXXX"
}
```





