# 获取云产品关联的指标列表 - GetProductMetrics

## 简介

获取云产品关联的指标列表






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetProductMetrics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetProductMetrics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductKey** | string | 产品唯一标识，参见 [产品概览]<br />（https://docs.ucloud.cn/cloudwatch/metric/intro） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*GetProductMetricsRespData*](#GetProductMetricsRespData) | 返回数据 |**Yes**|

#### 数据模型


#### GetProductMetricsRespData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Total** | int | 查询结果总数 |No|
| **List** | array[[*Metirc*](#Metirc)] | 指标列表 |No|
| **UnitConfigs** | array[[*MetricUnitConfig*](#MetricUnitConfig)] | 单位转换信息 |No|

#### Metirc

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProductType** | int | 云产品ID |No|
| **UnitID** | int | 单位ID |No|
| **MetricID** | int | 指标ID |No|
| **Metric** | string | 指标唯一标识 (uhost_cpu_usage) |No|
| **MetricEnName** | string | 指标英文名称 |No|
| **MetricChName** | string | 指标中文名称 |No|
| **MetricEnDesc** | string | 指标英文描述 |No|
| **MetricChDesc** | string | 指标中文描述 |No|
| **MetricGroup** | string | 指标分类/指标组 |No|
| **FrequencyMs** | int | 上报频率毫秒 |No|
| **Unit** | [*MetricUnit*](#MetricUnit) | 单位 |No|
| **CreatedBy** | string | 创建者 |No|
| **CreatedAt** | string | 创建时间 |No|
| **UpdatedBy** | string | 修改者 |No|
| **UpdatedAt** | string | 修改时间 |No|

#### MetricUnitConfig

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UnitCnNames** | array[string] | 指标中文名列表 |No|
| **UnitEnNames** | array[string] | 指标英文名列表 |No|
| **ConversionFactor** | int | 转换因子 |No|
| **ConversionRules** | array[[*ConversionRule*](#ConversionRule)] | 转换规则 |No|

#### ConversionRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **From** | string | 来源 |No|
| **To** | string | 目标 |No|
| **ConversionFactor** | int | 转换因子 |No|

#### MetricUnit

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UnitID** | int | 单位id |No|
| **GroupId** | int | GroupId |No|
| **UnitEnName** | string | 单位英文名称 |No|
| **UnitChName** | string | 单位中文名称 |No|
| **UnitDesc** | string | 单位描述 |No|
| **ConversionFactor** | int | 转换因子 |No|
| **CreatedBy** | string | 创建人 |No|
| **UpdatedBy** | string | 修改人 |No|
| **CreatedAt** | string | 创建时间 |No|
| **UpdatedAt** | string | 修改时间 |No|
| **DeletedAt** | int | 删除时间 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetProductMetrics
&ProductKey=jVhlepWB
&MetricGroup=XQkJSCbW
```

### 响应示例
    
```json
{
  "Action": "GetProductMetricsResponse",
  "Data": {
    "List": [
      {
        "ChartLabel": "",
        "CreatedAt": "2024-09-27T16:37:40+08:00",
        "CreatedBy": "admin",
        "DeletedAt": 0,
        "FrequencyMs": 60000,
        "Groups": [
          "GPU 卡数量监控"
        ],
        "ID": 781,
        "Metric": "cloudwatch_available_gpu_num_by_driver",
        "MetricChDesc": "",
        "MetricChName": "驱动识别的GPU卡数量",
        "MetricDesc": "",
        "MetricEnDesc": "",
        "MetricEnName": "cloudwatch_available_gpu_num_by_driver",
        "MetricGroup": "",
        "MetricID": 224968131907200,
        "MetricName": "驱动识别的GPU卡数量",
        "ProductType": 1,
        "Remark": "",
        "Unit": {
          "ConversionFactor": 1000,
          "CreatedAt": "2025-05-21T19:52:38+08:00",
          "CreatedBy": "admin",
          "DeletedAt": 0,
          "GroupId": 37,
          "UnitChName": "个",
          "UnitDesc": "counts",
          "UnitEnName": "counts",
          "UnitID": 26,
          "UnitName": "个",
          "UpdatedAt": "2025-05-28T15:45:48+08:00",
          "UpdatedBy": "admin"
        },
        "UnitID": 26,
        "UpdatedAt": "2025-03-03T23:11:58+08:00",
        "UpdatedBy": "admin"
      }
    ],
    "Total": 1,
    "UnitConfigs": [
      {
        "ConversionFactor": 1000,
        "ConversionRules": [
          {
            "ConversionFactor": 10,
            "From": "千个/s",
            "To": "万个/s"
          }
        ],
        "UnitCnNames": [
          "个/s",
          "千个/s",
          "万个/s",
          "千万个/s"
        ],
        "UnitEnNames": [
          "counts/s",
          "Thousand counts/s",
          "Ten thousand counts/s",
          "Ten Million counts/s"
        ],
        "UnitNames": [
          "个/s",
          "千个/s",
          "万个/s",
          "千万个/s"
        ]
      }
    ]
  },
  "RetCode": 0,
  "TotalCount": 1,
  "TraceId": "0ee3394b-c8d9-453c-b8a6-1b09f2fe5ad6"
}
```





