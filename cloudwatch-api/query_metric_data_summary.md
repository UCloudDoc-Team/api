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
| **Region** | string | 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ProductKey** | string | 产品唯一标识，参见 [产品概览](https://docs.ucloud.cn/cloudwatch/metric/intro) |**Yes**|
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
| **ResourceExtendAttrList** | array[[*ResourceExtendAttrItem*](#ResourceExtendAttrItem)] | 资源扩展属性列表 |No|
| **LabelAttrList** | array[[*LabelAttrItem*](#LabelAttrItem)] | 资源标签属性列表 |No|
| **CompanyId** | int | 公司id |No|
| **ResourceId** | string | 资源id |No|
| **Name** | string | 资源名称 |No|
| **RegionCN** | string | 地域中文名 |No|
| **ZoneCN** | string | 可用区中文 |No|
| **ProductKey** | string | 产品类型 |No|
| **OrganizationId** | int | 项目id |No|
| **Status** | int | 资源状态 |No|
| **MonitorAttr** | array[[*ResourceMonitorItem*](#ResourceMonitorItem)] | 资源的各项指标当前值列表 |No|

#### ResourceExtendAttrItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 键 |No|
| **Value** | string | 值 |No|

#### LabelAttrItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Key** | string | 键 |No|
| **Value** | string | 值 |No|

#### ResourceMonitorItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **MetricValues** | array[[*MetricSingleSample*](#MetricSingleSample)] | 指标数据数组 |No|

#### MetricSingleSample

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Metric** | string | 指标名 |No|
| **TagsList** | array[[*TagListItem*](#TagListItem)] | 指标标签列表 |No|
| **Value** | [*MetricSample*](#MetricSample) | 指标单个样本点对象 |No|

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
https://api.ucloud.cn/?Action=QueryMetricDataSummary
&Region=cn-zj
&ProjectId=KgGPGwaL
&ProductKey=pHLgbEMJ
&Offset=4
&Limit=5
&Metrics.N=ukkGIzHz
&ResourceIds.N=sooZntcO
```

### 响应示例
    
```json
{
  "Action": "QueryMetricDataSummaryResponse",
  "Data": {
    "List": [
      {
        "CompanyId": 0,
        "LabelAttrList": [],
        "MonitorAttr": [
          {
            "Metric": "DCBEKKCS",
            "MetricValues": [
              {
                "Metric": "JSXNSN",
                "TagsList": [
                  {
                    "Tag": "sadadas",
                    "TagValue": "dfadscdc"
                  },
                  {
                    "Tag": "adfeccfae",
                    "TagValue": "rtgtrce"
                  }
                ],
                "Value": {
                  "Timestamp": 1787307096,
                  "Value": 0
                }
              }
            ]
          }
        ],
        "Name": "asldejd",
        "OrganizationId": 0,
        "ProductKey": "oicndscn",
        "ProjectId": 0,
        "Region": "cn-guiyang1",
        "RegionCN": "西南（贵阳）",
        "ResourceExtendAttrList": [],
        "ResourceId": "SHCBBSj",
        "Status": 0,
        "Zone": "cn-guiyang1-01",
        "ZoneCN": "西南（贵阳）可用区A"
      }
    ],
    "Total": 1
  },
  "Message": "pQwRZNol",
  "RetCode": 0,
  "TotalCount": 1,
  "TraceId": "LjdXqSzW"
}
```





