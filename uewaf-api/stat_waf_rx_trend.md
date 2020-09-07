# 获取WAF上行流量趋势 - StatWafRXTrend

## 简介

获取WAF上行流量趋势









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StatWafRXTrend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 开始时间，时间错，单位：秒 |**Yes**|
| **EndTime** | int | 结束时间，时间戳，单位：秒 |**Yes**|
| **Domain** | string | 域名 |No|
| **Method** | string | min,avg,max,默认为max |No|
| **Extent** | int | 统计区间，单位：秒，取值范围0-7200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*StatRXResult*](#StatRXResult) | 上行流量趋势统计结果，参考StatRXResult |No|

#### 数据模型


#### StatRXResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 返回节点个数 |**Yes**|
| **Uint** | string | 流量计量单位 |**Yes**|
| **Detail** | array[[*StatRXDetail*](#StatRXDetail)] | 上行流量详情，参考StatRXDetail |No|

#### StatRXDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Timestamp** | int | 时间戳 |**Yes**|
| **Waf** | int | waf上行流量 |**Yes**|
| **Src** | int | 源站上行流量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StatWafRXTrend
&ProjectId=org-xxx
&BeginTime=1586231349
&EndTime=1586231408
&Domain=www.test.com
&Method=avg
```

### 响应示例
    
```json
{
  "Action": "StatWafRXTrendResponse",
  "Result": {
    "Count": 61,
    "Detail": [
      {
        "Src": 117,
        "Timestamp": 1586227440,
        "Waf": 137
      }
    ],
    "Type": "RX",
    "Unit": "bps"
  },
  "RetCode": 0
}
```





