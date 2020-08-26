# 获取WAF下行流量趋势 - StatWafTXTRend

## 简介

获取WAF下行流量趋势









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StatWafTXTRend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 开始时间，时间戳，单位：秒 |**Yes**|
| **EndTime** | int | 结束时间，时间戳，单位：秒 |**Yes**|
| **Method** | string | min，avg，max，默认为‘max’ |No|
| **Domain** | string | 域名 |No|
| **Extent** | int | 统计区间，单位：秒，取值范围0-7200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | array[[*StatTXResult*](#StatTXResult)] | 下行流量统计信息，参考StatTXResult |No|

#### 数据模型


#### StatTXResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 返回节点个数 |**Yes**|
| **Unit** | string | 流量计量单位 |**Yes**|
| **Detail** | array[[*StatTXDetail*](#StatTXDetail)] | 下行流量详情列表，参考StatTXDetail |**Yes**|

#### StatTXDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间戳 |**Yes**|
| **Waf** | int | waf下行流量 |**Yes**|
| **Src** | int | 源站下行流量 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StatWafTXTRend
&ProjectId=org-xxx
&BeginTime=1586231349
&EndTime=1586231408
&Method=avg
&Domain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "StatWafTXTrendResponse",
  "Result": {
    "Count": 61,
    "Detail": [
      {
        "Src": 583,
        "Timestamp": 1586227440,
        "Waf": 583
      }
    ],
    "Type": "TX",
    "Unit": "bps"
  },
  "RetCode": 0
}
```





