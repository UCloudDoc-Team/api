# 获取容器实例指标 - GetCubeMetrics

## 简介

获取容器实例指标









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetCubeMetrics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ResourceId** | string | 资源ID |**Yes**|
| **MetricName** | string | 指标名称 |**Yes**|
| **ContainerName** | string | 容器名称 |**Yes**|
| **BeginTime** | string | 开始时间 |**Yes**|
| **EndTime** | string | 结束时间 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSets** | array[[*MetricDataSet*](#MetricDataSet)] | 指标数据 |**Yes**|

#### 数据模型


#### MetricDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **MetricName** | string |  |No|
| **Values** | array[[*ValueSet*](#ValueSet)] |  |No|

#### ValueSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Value** | float |  |**Yes**|
| **Timestamp** | int |  |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetCubeMetrics
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=LoHXHEXA
&ResourceId=pZzLCAZu
&MetricName=xRIpRYSn
&ContainerName=aObwrsvs
&BeginTime=cQtOVblh
&EndTime=DCDovlbg
```

### 响应示例
    
```json
{
  "Action": "GetCubeMetricsResponse",
  "DataSets": [
    {
      "MetricName": "DBzVWebn",
      "Values": [
        {
          "Timestamp": 8,
          "Value": 8.96588
        }
      ]
    }
  ],
  "RetCode": 0
}
```





