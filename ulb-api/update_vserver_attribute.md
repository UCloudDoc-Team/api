# 更新VServer属性 - UpdateVServerAttribute

## 简介

更新VServer实例属性



!> VServerId 对应 CreateVServer 返回的 VServerId<br />或者 DescribeVServer / DescribeULB 返回的 ULBVServerSet 中的 VServerId<br /><br />没有传的参数都不会做修改


## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=UpdateVServerAttribute)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `UpdateVServerAttribute`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ULBId** | string | 负载均衡实例ID |**Yes**|
| **VServerId** | string | VServer实例ID |**Yes**|
| **VServerName** | string | VServer实例名称，若无此字段则不做修改 |No|
| **Method** | string | VServer负载均衡模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）; WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数；Backup -> 主备模式。<br />ConsistentHash，SourcePort，ConsistentHashPort 只在报文转发中使用；Leastconn只在请求代理中使用；Roundrobin、Source和WeightRoundrobin,Backup在请求代理和报文转发中使用。<br />默认为："Roundrobin" |No|
| **PersistenceType** | string | VServer会话保持模式，若无此字段则不做修改。枚举值：None：关闭；ServerInsert：自动生成KEY；UserDefined：用户自定义KEY。 |No|
| **PersistenceInfo** | string | 根据PersistenceType确定: None或ServerInsert, 此字段无意义; UserDefined, 则此字段传入用户自定义会话保持String. 若无此字段则不做修改 |No|
| **ClientTimeout** | int | 请求代理的VServer下表示空闲连接的回收时间，单位：秒，取值范围：时(0，86400]，默认值为60；报文转发的VServer下表示回话保持的时间，单位：秒，取值范围：[60，900]，0 表示禁用连接保持 |No|
| **MonitorType** | string | 健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；Ping -> Ping探测，Customize -> UDP检查<br /><br />请求代理型默认值为Port，其中TCP协议仅支持Port，其他协议支持Port和Path;<br />报文转发型TCP协议仅支持Port，UDP协议支持Ping、Port和Customize，默认值为Ping |No|
| **Domain** | string | MonitorType 为 Path 时指定健康检查发送请求时HTTP HEADER 里的域名 |No|
| **Path** | string | MonitorType 为 Path 时指定健康检查发送请求时的路径，默认为 / |No|
| **RequestMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查发出的请求报文 |No|
| **ResponseMsg** | string | 根据MonitorType确认； 当MonitorType为Customize时，此字段有意义，代表UDP检查请求应收到的响应报文 |No|
| **SecurityPolicyId** | string | 安全策略组ID |No|
| **EnableCompression** | int | 0:关闭 1:开启，用于数据压缩功能 |No|
| **ForwardPort** | int | 重定向端口，取值范围[0-65535]；默认值为0，代表关闭；仅HTTP协议支持开启重定向功能 |No|
| **EnableHTTP2** | int | 0:关闭 1:开启，用于开启http2功能；默认值为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=UpdateVServerAttribute
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBId=ulb-XXXX
&VServerId=vserver-XXXX
&VServerName=Testapi
&Protocol=HTTP 
&Method=Roundrobin
&PersistenceType=None
&PersistenceInfo=None
&ClientTimeout=60
&MonitorType=Port
&EnableHTTP2=9
&RequestMsg=QHpxxRrA
&ResponseMsg=rVBUBWIh
&SecurityPolicyId=cbupUwHT
&EnableCompression=5
&ForwardPort=4
&EnableHTTP2=1
```

### 响应示例
    
```json
{
  "Action": "UpdateVServerAttributeResponse",
  "RetCode": 0
}
```





