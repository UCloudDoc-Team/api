# 获取资源看图属性列表 - QueryMetricDataSummary

## 简介

获取资源看图属性列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=QueryMetricDataSummary)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryMetricDataSummary`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域，全局产品可以不传，其他必传 |**Yes**|
| **ProjectId** | string | 项目ID。 |**Yes**|
| **ProductKey** | string | 产品类型 |**Yes**|
| **Offset** | int | 跳过的数量 |**Yes**|
| **Limit** | int | 当前页数据尺寸 |**Yes**|
| **Metrics.N** | string | 指定要查询的指标列表，不指定则使用默认的指标集合 |No|
| **ResourceIds.N** | string | 指定要查询的资源ID列表 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TraceId** | string | 链路id |No|
| **TotalCount** | int | 总数 |No|
| **Data** | [*QueryMetricDataSummaryRespData*](#QueryMetricDataSummaryRespData) | 数据 |No|

#### 数据模型


#### QueryMetricDataSummaryRespData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 总数 |No|
| **List** | array[[*ResourceSummary*](#ResourceSummary)] | 结果集 |No|

#### ResourceSummary

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |No|
| **Zone** | string | 可用区 |No|
| **ProjectId** | int | 项目id |No|
| **CompanyId** | int | 公司id |No|
| **ResourceId** | string | 资源id |No|
| **Name** | string | 资源名称 |No|
| **RegionCN** | string | 地域中文名 |No|
| **ZoneCN** | string | 可用区中文 |No|
| **ProductKey** | string | 产品类型 |No|
| **OrganizationId** | int | 项目id |No|
| **Status** | int | 资源状态 |No|
| **MonitorAttr** | array[[*ResourceMonitorItem*](#ResourceMonitorItem)] | 资源的各项指标当前值，类型为：<br />map[string][]MetricSingleSample<br />map的key为指标名，value为样本点数组。 |No|

#### ResourceMonitorItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **MetricValues** | array[[*MetricSingleSample*](#MetricSingleSample)] | 指标数据数组 |No|

#### MetricSingleSample

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **Tags** | object | 指标的tag的k-v对象 |No|
| **Value** | [*MetricSample*](#MetricSample) | 指标单个样本点对象 |No|

#### MetricSample

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | float | 时间戳 |No|
| **Value** | float | 样本值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryMetricDataSummary
&Region=cn-zj
&ProjectId=CXUBJRIx
&ProductKey=jRIQzjck
&Offset=9
&Limit=3
&Metrics.N=mZHSOGcV
&ResourceIds.N=gYnDoDyh
```

### 响应示例
    
```json
{
  "Action": "QueryMetricDataSummaryResponse",
  "Data": {},
  "Message": "XNlHoNgi",
  "RetCode": 0,
  "TotalCount": 7,
  "TraceId": "vSFARHxW"
}
```





