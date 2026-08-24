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
| **Region** | string | 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ProductKey** | string | 产品唯一标识，参见 [产品概览](https://docs.ucloud.cn/cloudwatch/metric/intro) |**Yes**|
| **StartTime** | int | 开始时间，值为10位数时间戳 |**Yes**|
| **EndTime** | int | 截止时间，值为10位数时间戳 |**Yes**|
| **CalcMethod** | string | 计算方式，枚举值如下：<br />raw:原始值,<br />max:最大值,<br />min:最小值,<br />avg:平均值,<br />sum:求和 |**Yes**|
| **Period** | int | 周期，单位为秒，即：数据查询时，返回数据点的时间间隔。<br />不同的查询时间范围，对应的周期不同：<br />0<时间范围<=1h——周期：1分钟/5分钟，对应的枚举值为60、300；<br /><br />1h<时间范围<=12h——周期：1分钟/5分钟/1小时，对应的枚举值为60、300、3600；<br /><br />12h<时间范围<=24h——周期：5分钟/1小时，对应的枚举值为300、3600；<br /><br />1天<时间范围<=30天——周期：1小时/6小时/24小时，对应的枚举值为3600、21600、86400 |**Yes**|
| **MetricInfos.N.Metric** | string | 指标名，参数中N的取值范围为 0～9 |**Yes**|
| **MetricInfos.N.ResourceId** | string | 指标所属资源id，参数中N的取值范围为 0～9 |**Yes**|
| **MetricInfos.N.TagOperation** | string | 多个 Tag 条件的匹配方式；可选 and（默认）或 or。TagList 中使用 or 时最多支持 3 个 Tag。 |No|
| **MetricInfos.N.TagList.N.TagKey** | string | 要查询指标的Tag的key，参数中N的取值范围为 0～9 |No|
| **MetricInfos.N.TagList.N.TagValues.N** | string | 要查询指标的Tag的Value，参数中N的取值范围为 0～9 |No|

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
https://api.ucloud.cn/?Action=QueryMetricDataSet
&Region=cn-zj
&ProjectId=fZodyYbz
&ProductKey=wOQpJcBt
&StartTime=8
&EndTime=6
&CalcMethod=raw
&Period=60
&MetricInfos.N.Metric=OBWiRglC
&MetricInfos.N.ResourceId=jaGTgWpR
&MetricInfos.N.TagOperation=GweoaGaC
&MetricInfos.N.TagList.N.TagKey=ffixFIkd
&MetricInfos.N.TagList.N.TagValues.N=lTmpMkgU
```

### 响应示例
    
```json
{
  "Action": "QueryMetricDataSetResponse",
  "Data": {
    "InvalidResourceIds": [],
    "List": [
      {
        "ErrCode": 0,
        "ErrMsg": "",
        "Metric": "cloudwatch_data_disk_used_per",
        "Results": [
          {
            "ResourceId": "uhost-xxx",
            "ResourceName": "UHost",
            "TagList": [
              {
                "Tag": "disk",
                "TagValue": "/dev/vda15"
              },
              {
                "Tag": "mount",
                "TagValue": "/boot/efi"
              }
            ],
            "Values": [
              {
                "Timestamp": 1787303495,
                "Value": 5.85
              },
              {
                "Timestamp": 1787303795,
                "Value": 5.85
              },
              {
                "Timestamp": 1787304095,
                "Value": 5.85
              },
              {
                "Timestamp": 1787304395,
                "Value": 5.85
              },
              {
                "Timestamp": 1787304695,
                "Value": 5.85
              },
              {
                "Timestamp": 1787304995,
                "Value": 5.85
              },
              {
                "Timestamp": 1787305295,
                "Value": 5.85
              },
              {
                "Timestamp": 1787305595,
                "Value": 5.85
              },
              {
                "Timestamp": 1787305895,
                "Value": 5.85
              },
              {
                "Timestamp": 1787306195,
                "Value": 5.85
              },
              {
                "Timestamp": 1787306495,
                "Value": 5.85
              },
              {
                "Timestamp": 1787306795,
                "Value": 5.85
              },
              {
                "Timestamp": 1787307095,
                "Value": 5.85
              }
            ]
          },
          {
            "ResourceId": "uhost-xxx",
            "ResourceName": "UHost",
            "TagList": [
              {
                "Tag": "mount",
                "TagValue": "/boot"
              },
              {
                "Tag": "disk",
                "TagValue": "/dev/vda16"
              }
            ],
            "Values": [
              {
                "Timestamp": 1787303495,
                "Value": 9.46
              },
              {
                "Timestamp": 1787303795,
                "Value": 9.46
              },
              {
                "Timestamp": 1787304095,
                "Value": 9.46
              },
              {
                "Timestamp": 1787304395,
                "Value": 9.46
              },
              {
                "Timestamp": 1787304695,
                "Value": 9.46
              },
              {
                "Timestamp": 1787304995,
                "Value": 9.46
              },
              {
                "Timestamp": 1787305295,
                "Value": 9.46
              },
              {
                "Timestamp": 1787305595,
                "Value": 9.46
              },
              {
                "Timestamp": 1787305895,
                "Value": 9.46
              },
              {
                "Timestamp": 1787306195,
                "Value": 9.46
              },
              {
                "Timestamp": 1787306495,
                "Value": 9.46
              },
              {
                "Timestamp": 1787306795,
                "Value": 9.46
              },
              {
                "Timestamp": 1787307095,
                "Value": 9.46
              }
            ]
          },
          {
            "ResourceId": "uhost-xxx",
            "ResourceName": "UHost",
            "TagList": [
              {
                "Tag": "disk",
                "TagValue": "/dev/vdb"
              },
              {
                "Tag": "mount",
                "TagValue": "/data"
              }
            ],
            "Values": [
              {
                "Timestamp": 1787303495,
                "Value": 0
              },
              {
                "Timestamp": 1787303795,
                "Value": 0
              },
              {
                "Timestamp": 1787304095,
                "Value": 0
              },
              {
                "Timestamp": 1787304395,
                "Value": 0
              },
              {
                "Timestamp": 1787304695,
                "Value": 0
              },
              {
                "Timestamp": 1787304995,
                "Value": 0
              },
              {
                "Timestamp": 1787305295,
                "Value": 0
              },
              {
                "Timestamp": 1787305595,
                "Value": 0
              },
              {
                "Timestamp": 1787305895,
                "Value": 0
              },
              {
                "Timestamp": 1787306195,
                "Value": 0
              },
              {
                "Timestamp": 1787306495,
                "Value": 0
              },
              {
                "Timestamp": 1787306795,
                "Value": 0
              },
              {
                "Timestamp": 1787307095,
                "Value": 0
              }
            ]
          }
        ],
        "TagEntries": [
          {
            "KeyList": [
              "/boot/efi",
              "/boot",
              "/data"
            ],
            "TagName": "mount"
          },
          {
            "KeyList": [
              "/dev/vda15",
              "/dev/vda16",
              "/dev/vdb"
            ],
            "TagName": "disk"
          }
        ]
      }
    ]
  },
  "Message": "",
  "RetCode": 0,
  "TraceId": "9f7bf6aa-9b9f-49e1-b873-68989d2b917e"
}
```





