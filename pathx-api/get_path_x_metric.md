# 获取全球加速监控信息 - GetPathXMetric

## 简介

获取全球加速监控信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetPathXMetric)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetPathXMetric`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。请参考[GetProjectList接口](api/summary/get_project_list) |**Yes**|
| **ResourceId** | string | ResourceId，如upath ID  和 uga ID  |**Yes**|
| **BeginTime** | int | 查询起始时间，10位长度时间戳 |**Yes**|
| **EndTime** | int | 查询结束时间，10位长度时间戳 |**Yes**|
| **MetricName.N** | string | 查询监控的指标项。目前仅允许以下四项：NetworkOut:出向带宽，NetworkIn:入向带宽，NetworkOutUsage:出向带宽使用率，NetworkInUsage:入向带宽使用率 |**Yes**|
| **ResourceType** | string | upath:加速线路,uga:加速实例 |**Yes**|
| **LineId** | string | 具体线路id，调用DescribePathXLineConfig接口获取线路列表 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*MetricPeriod*](#MetricPeriod)] | 监控数据结果集 |No|

#### 数据模型


#### MetricPeriod

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NetworkOut** | array[[*MatricPoint*](#MatricPoint)] | 出向带宽 |No|
| **NetworkIn** | array[[*MatricPoint*](#MatricPoint)] | 入向带宽 |No|
| **NetworkOutUsage** | array[[*MatricPoint*](#MatricPoint)] | 出向带宽使用率 |No|
| **NetworkInUsage** | array[[*MatricPoint*](#MatricPoint)] | 入向带宽使用率 |No|

#### MatricPoint

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳  |No|
| **Value** | int | 监控点数值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetPathXMetric
&ProjectId=org-ejcxxx
&ResourceType=upath
&ResourceId=upath-1boe2u
&BeginTime=1568797253
&EndTime=1568800853
&LineId=line_cn_afr-nigeria
&MetricName.0=NetworkOutUsage
&MetricName.1=NetworkInUsage
```

### 响应示例
    
```json
{
  "Action": "GetPathXMetricResponse",
  "DataSet": {
    "NetworkIn": null,
    "NetworkInUsage": [
      {
        "Timestamp": 1568797260,
        "Value": 12
      },
      {
        "Timestamp": 1568797320,
        "Value": 18
      },
      {
        "Timestamp": 1568797380,
        "Value": 17
      },
      {
        "Timestamp": 1568797440,
        "Value": 17
      }
    ],
    "NetworkOut": null,
    "NetworkOutUsage": [
      {
        "Timestamp": 1568797260,
        "Value": 14
      },
      {
        "Timestamp": 1568797320,
        "Value": 23
      },
      {
        "Timestamp": 1568797380,
        "Value": 21
      },
      {
        "Timestamp": 1568797440,
        "Value": 20
      }
    ]
  },
  "Message": "",
  "RetCode": 0
}
```





