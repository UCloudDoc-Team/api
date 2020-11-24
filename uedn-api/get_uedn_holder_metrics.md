# 获取容器监控数据 - GetUEdnHolderMetrics

## 简介

获取容器（CPU利用率，带宽，内存）数据









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUEdnHolderMetrics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **PackName** | string | 容器名称 |**Yes**|
| **Type.N** | string | n为0 CPU利用率, 1内存使用率, 2网卡出带宽, 3网卡入带宽, 4网卡出包数, 5网卡入包数 |**Yes**|
| **ResourceId** | string | 容器组资源id |**Yes**|
| **StartTime** | int | 开始时间 |No|
| **EndTime** | int | 结束时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSets** | array[[*MetricisDataSet*](#MetricisDataSet)] | 获得的监控数据（详情参考MetricisDataSet） |**Yes**|

#### 数据模型


#### MetricisDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CPUUtilization** | array[[*MonitorInfo*](#MonitorInfo)] | cpu利用率（详情参考MonitorInfo） |No|
| **MemUtilization** | array[string] | 内存使用率（详情参考MonitorInfo） |No|
| **NetPacketOut** | array[string] | 网卡出包数（详情参考MonitorInfo） |No|
| **NetPacketIn** | array[string] | 网卡入包数（详情参考MonitorInfo） |No|
| **NICOut** | array[string] | 网卡出带宽（详情参考MonitorInfo） |No|
| **NICIn** | array[string] | 网卡入带宽（详情参考MonitorInfo） |No|

#### MonitorInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间戳 |**Yes**|
| **Value** | int | 值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUEdnHolderMetrics
&ProjectId=uOlEuMoy
&PackName=jUJnXZBl
&Type.n=woHMbpHy
&ResourceId=xApyIeyc
&StartTime=9
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "GetUEdnHolderMetricsResponse",
  "DataSets": [
    {
      "CPUUtilization": [
        {
          "TimeStamp": 3,
          "Value": 4
        }
      ],
      "MemUtilization": [
        "NvUGZEBA"
      ],
      "NICIn": [
        "zVZeeReG"
      ],
      "NICOut": [
        "RGPsxmJo"
      ],
      "NetPacketIn": [
        "gsHoPZCv"
      ],
      "NetPacketOut": [
        "pHcrfDDQ"
      ]
    }
  ],
  "RetCode": 0
}
```





