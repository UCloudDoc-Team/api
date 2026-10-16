# 获取指标数据聚合方式 - GetMetricDataAggregationMethod

## 简介

获取指标数据聚合方式






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetMetricDataAggregationMethod)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetMetricDataAggregationMethod`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*GetMetricDataAggregationMethodResp*](#GetMetricDataAggregationMethodResp) | 获取指标数据聚合方式返回结果 |**Yes**|

#### 数据模型


#### GetMetricDataAggregationMethodResp

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **List** | array[[*MetricDataAggregationMethod*](#MetricDataAggregationMethod)] | 聚合方式列表 |**Yes**|

#### MetricDataAggregationMethod

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Label** | string | 标签 |**Yes**|
| **Value** | string | 值 |**Yes**|
| **IsDefault** | boolean | 是否是默认方式 |**Yes**|
| **Description** | string | 描述 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetMetricDataAggregationMethod
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=WhuzvDHN
```

### 响应示例
    
```json
{
  "Action": "GetMetricDataAggregationMethodResponse",
  "Data": {},
  "RetCode": 0
}
```





