# 获取监控数据 - GetMetric

## 简介

获取监控数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) / [JavaScript](https://github.com/ucloud/ucloud-sdk-js) / [PHP](https://github.com/ucloud/ucloud-sdk-php) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetMetric)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetMetric`                        | **Yes** |
| **PublicKey**  | string  | AccessKey ID，在 [控制台](https://console.ucloud.cn/uaccount/api_manage) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID，不填为默认项目。子账户必须填写项目ID |No|
| **ResourceType** | string | 资源类型 |**Yes**|
| **MetricName.N** | string | 指标名称（不同ResourceType对应不同的MetricName） |**Yes**|
| **ResourceId** | string | 资源Id（目前除sharebandwidth可以不传入ResourceId外，其他资源必须传入，sharebandwidth不传入会默认使用获取到的第一个资源Id） |No|
| **TimeRange** | int | 拉取最近多少秒的监控数据，默认1小时，即3600；最大1个月 |No|
| **BeginTime** | int | 起始时间unixtimestamp，若传入TimeRange，此项忽略 |No|
| **EndTime** | int | 结束时间unixtimestamp，若传入TimeRange，此项忽略；若只传入BeginTime，此项默认为当前时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSets** | [*DataSet*](#DataSet) | 数据 |No|

#### 数据模型


#### DataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳 |**Yes**|
| **Value** | int | 值 |**Yes**|
| **IP** | string | 数据源IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetMetric
&Region=CUPCMnhu
&Zone=xmiktFHL
&ProjectId=AeeicJWM
&ResourceType=iAqCBPNi
&MetricName.n=afvAGmoZ
&ResourceId=eNRBsUET
&TimeRange=NaN
&BeginTime=1
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "GetMetricResponse",
  "DataSet": {},
  "Message": "tslFtPXU",
  "RetCode": 0
}
```





