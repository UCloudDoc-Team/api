# 获取Cube实例监控数据 - GetCubeMetrics

## 简介

获取Cube实例（Pod，PodX，Deploy等）监控数据时间序列









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
| **ResourceId** | string | Cube实例资源ID |**Yes**|
| **MetricName.N** | string | 监控指标名称 |**Yes**|
| **BeginTime** | int | 开始时间 |**Yes**|
| **EndTime** | int | 结束时间，必须大于开始时间 |**Yes**|
| **ContainerName** | string | Pod内容器名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSets** | array[[*MetricDataSet*](#MetricDataSet)] | 时间序列集合 |No|

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
&ProjectId=RLhqBcar
&ResourceId=bCkoRYdG
&MetricName.0=QYLScIJF
&MetricName.1=EtAsnhYu
&MetricName.2=QslxcNfy
&StartTime=1595834524
&EndTime=1595840000
&ContainerName=hWruSNVy
```

### 响应示例
    
```json
{
  "Action": "GetCubeMetricsResponse",
  "Data": {},
  "Message": "LpnSIBIB",
  "RetCode": 0
}
```





