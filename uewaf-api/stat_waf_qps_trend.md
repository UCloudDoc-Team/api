# 获取WAF QPS趋势 - StatWafQPSTrend

## 简介

获取WAF QPS趋势









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StatWafQPSTrend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填表示默认项目 |No|
| **BeginTime** | int | 起始时间戳,单位：秒 |**Yes**|
| **EndTime** | int | 终止时间戳,单位：秒 |**Yes**|
| **Method** | string | 取点方式max\|min\|avg,默认取平均值avg |No|
| **Domain** | string | 要过滤的域名,统计所有域名时不传该参数或者传空字符串 |No|
| **Extent** | int | 统计区间，单位：秒，取值范围0-7200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Detail** | [*QPSStatResult*](#QPSStatResult) | QPS趋势流量统计结果，参考QPSStatResult |No|

#### 数据模型


#### QPSStatResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 采样点个数 |**Yes**|
| **Detail** | array[[*QPSTrendDetail*](#QPSTrendDetail)] | QPS统计结果集合，参考QPSTrendDetail |**Yes**|

#### QPSTrendDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间戳 |**Yes**|
| **SrcQPS** | string | 到源站qps |**Yes**|
| **WafQPS** | string | 到WAF的qps |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StatWafQPSTrend
&ProjectId=org-xxx
&BeginTime=1586231349
&EndTime=1586231460
&Domain=www.test.com
&Method=min
```

### 响应示例
    
```json
{
  "Action": "StatWafQPSTrendResponse",
  "Result": {
    "Count": 1,
    "Detail": [
      {
        "SrcQps": 1,
        "Timestamp": 1586227440,
        "WafQps": 1
      }
    ],
    "Type": "QPS"
  },
  "RetCode": 0
}
```





