# 获取全地域加速监控信息 - GetUGA3Metric

## 简介

获取全地域加速监控信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUGA3Metric)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUGA3Metric`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 资源ID |**Yes**|
| **BeginTime** | int | 查询起始时间，10位长度时间戳 |**Yes**|
| **EndTime** | int | 查询结束时间，10位长度时间戳 |**Yes**|
| **MetricName.N** | string | 查询监控的指标项。可不传<br />	NetworkOut:出口总带宽<br />	NetworkIn：入口总带宽<br />	NetworkOutUsage：出口带宽使用率<br />	NetworkInUsage：入口总带宽使用率<br />	NetworkOutSubline ：子线路出口带宽<br />	NetworkInSubline：子线路入口带宽<br />	Delay：线路平均延迟<br />	DelaySubline：子线路延迟<br />	ConnectCount：当前连接数<br />	ConnectCountSubline：子线路当前连接数<br />	DelayPromote：延迟提升<br />	DelayPromoteSubline：子线路延迟提升 |No|
| **IsSubline** | boolean | 是否为子线路。为了简化查询,true 会返回所有子线路监控项可以，false:返回所有汇总的监控数据 |No|
| **AreaCode** | string | 子线路AreaCode ,子线路的时候传，不是子线路可以不传 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | [*UGA3Metric*](#UGA3Metric) | 监控数据结果集 |No|

#### 数据模型


#### UGA3Metric

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NetworkOut** | array[[*MatricPoint*](#MatricPoint)] | 出向带宽 |No|
| **NetworkIn** | array[[*MatricPoint*](#MatricPoint)] | 入向带宽 |No|
| **NetworkOutUsage** | array[[*MatricPoint*](#MatricPoint)] | 出向带宽使用率 |No|
| **NetworkInUsage** | array[[*MatricPoint*](#MatricPoint)] | 入向带宽使用率 |No|
| **NetworkOutSubline** | array[[*MatricPoint*](#MatricPoint)] | 子线路出口带宽 |No|
| **NetworkInSubline** | array[[*MatricPoint*](#MatricPoint)] | 子线路入口带宽 |No|
| **Delay** | array[[*MatricPoint*](#MatricPoint)] | 线路平均延迟 |No|
| **DelaySubline** | array[[*MatricPoint*](#MatricPoint)] | 子线路延迟 |No|
| **DelayPromote** | array[[*MatricPoint*](#MatricPoint)] | 延迟提升 |No|
| **DelayPromoteSubline** | array[[*MatricPoint*](#MatricPoint)] | 子线路延迟提升 |No|
| **ConnectCount** | array[[*MatricPoint*](#MatricPoint)] | 当前连接数 |No|
| **ConnectCountSubline** | array[[*MatricPoint*](#MatricPoint)] | 子线路当前连接数 |No|

#### MatricPoint

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳  |No|
| **Value** | int | 监控点数值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUGA3Metric
&ProjectId=eXaSylDy
&ResourceId=VfqnFVtV
&BeginTime=2
&EndTime=7
&MetricName.n=SBeQbegI
&ResourceType=upath
&LineId=MpdrliRw
```

### 响应示例
    
```json
{
  "Action": "GetUGA3MetricResponse",
  "DataSet": {},
  "RetCode": 0
}
```





