# 获取高精度指标样本数据 - QueryMetricDenseData

## 简介

获取高精度指标样本数据






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryMetricDenseData)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryMetricDenseData`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 全局产品可不传，其他类型必传。 |No|
| **ProjectId** | string | 项目ID |No|
| **ProductKey** | string | 资源类型 |**Yes**|
| **StartTime** | int | 开始时间戳 |**Yes**|
| **EndTime** | int | 截止时间戳 |**Yes**|
| **MetricInfos.N.Metric** | string | 指标名 |No|
| **MetricInfos.N.ResourceId** | string | 资源id |No|
| **MetricInfos.N.Tags.AnyKey** | string | AnyKey：代表任意一个用户自定义的key。<br />Tags是一个用户自定义对象map，是要查询指标的tag的key和value。<br />用户自定义的Tags对象里的key和value，它们分别是要查询的tag的key和value。如：<br />"Tags":{<br />  "tag1":"value1",<br />  "tag2":"value2",<br />  "tag3":"value3"<br />} |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*QueryMetricDataResp*](#QueryMetricDataResp) | 返回高精度指标监控数据 |No|

#### 数据模型


#### QueryMetricDataResp

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **InvalidResourceIds** | array[string] | 无效或无权限资源的 ID 列表 |No|
| **List** | array[[*QueryMetricDataRespItem*](#QueryMetricDataRespItem)] | 查询的结果集 |No|

#### QueryMetricDataRespItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **ErrCode** | int | 该指标查询的处理状态码 |No|
| **ErrMsg** | string | 该指标查询的状态说明 |No|
| **TagEntries** | array[[*TagEntry*](#TagEntry)] | 标签列表。每项为 TagEntry：TagName（标签名）和 KeyList（该标签的全部候选值）。 |No|
| **Results** | array[[*MetricResult*](#MetricResult)] | 查询到的时间序列列表 |No|

#### TagEntry

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TagName** | string | 标签名称 |No|
| **KeyList** | array[string] | 标签候选值列表 |No|

#### MetricResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源的短id |No|
| **ResourceName** | string | 资源名称 |No|
| **TagList** | array[[*TagListItem*](#TagListItem)] | 资源标签列表。每项为 TagListItem：Tag（标签名）和 TagValue（标签值）。 |No|
| **Values** | array[[*MetricSample*](#MetricSample)] | 指标数据点列表，元素为 MetricPoint |No|

#### TagListItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Tag** | string | 标签名 |No|
| **TagValue** | string | 标签值 |No|

#### MetricSample

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳 |No|
| **Value** | float | 样本值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryMetricDenseData
&Region=cn-zj
&ProjectId=RKqqwnaX
&ProductKey=TcritUYT
&StartTime=1
&EndTime=4
&MetricInfos.N.Metric=MAuoFcLS
&MetricInfos.N.ResourceId=bDFuWdlA
&MetricInfos.N.Tags.AnyKey=zBerlldy
```

### 响应示例
    
```json
{
  "Action": "QueryMetricDenseDataResponse",
  "Data": {},
  "Message": "WAMdwwGi",
  "RetCode": 0
}
```





