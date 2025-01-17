# 查询监控指标数据集 - QueryMetricDataSet

## 简介

查询监控指标数据集






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryMetricDataSet)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryMetricDataSet`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 全局产品可不传，其他类型必传。 |**Yes**|
| **ProjectId** | string | 项目ID。 |**Yes**|
| **ProductKey** | string | 资源类型 |**Yes**|
| **StartTime** | int | 开始时间 |**Yes**|
| **EndTime** | int | 截止时间 |**Yes**|
| **MetricInfos.N.Metric** | string | 指标名 |**Yes**|
| **MetricInfos.N.ResourceId** | string | 指标所属资源id |**Yes**|
| **TagList.N.TagKey** | string | 要查询指标的Tag的key |No|
| **TagValues.N** | string | 要查询指标的Tag的Value |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TraceId** | string | 日志链路id |No|
| **Data** | [*QueryMetricDataResp*](#QueryMetricDataResp) | QueryMetricDataResp |No|

#### 数据模型


#### QueryMetricDataResp

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **List** | array[[*QueryMetricDataRespItem*](#QueryMetricDataRespItem)] | 查询的结果集 |No|

#### QueryMetricDataRespItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **Tags** | object | 指标查询结果的所有tag的key和对应的所有value数组。<br /><br />Tags格式为，key为tagkey字符串，value为tagValue的字符串数组。 |No|
| **Results** | array[[*MetricResult*](#MetricResult)] |  |No|

#### MetricResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源的短id |No|
| **TagMap** | object | TagMap是一个对象，key和value均为字符串。<br />TagMap返回当前series的所有的tag的key和value。 |No|
| **Values** | array[[*MetricSample*](#MetricSample)] |  |No|

#### MetricSample

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳 |No|
| **Value** | float | 样本值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryMetricDataSet
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=lBXDBARv
&ProductKey=YoLcjjOJ
&StartTime=2
&EndTime=1
&MetricInfos.N.Metric=wBhLvIzA
&MetricInfos.N.ResourceId=pAlImMnm
&MetricInfos.N.TagList.N.TagKey=bYSOyCNH
&MetricInfos.N.TagList.N.TagValues.N=jNRAlNmm
```

### 响应示例
    
```json
{
  "Action": "QueryMetricDataSetResponse",
  "Data": {},
  "Message": "nPOVsgEJ",
  "RetCode": 0,
  "TraceId": "wbgFGCpd"
}
```





