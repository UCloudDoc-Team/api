# 获取WAF请求数趋势 - StatWafReqsTrend

## 简介

获取WAF请求数趋势








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `StatWafReqsTrend`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 起始时间戳,单位 秒 |**Yes**|
| **EndTime** | int | 终止时间戳,单位 秒 |**Yes**|
| **Domain** | string | 如果查看指定域名的统计信息,传入域名,否则不传该参数,或者传空字符串 |No|
| **Extent** | int | 统计区间，单位：秒，取值范围0-7200 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Result** | [*StatReqsResult*](#StatReqsResult) | 请求数趋势统计结果，参考StatReqsResult |No|

#### 数据模型


#### StatReqsResult

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 返回节点个数 |**Yes**|
| **Detail** | array[[*StatReqsDetail*](#StatReqsDetail)] | 请求数统计详细信息列表，参考StatReqsDetail |**Yes**|

#### StatReqsDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间戳 |**Yes**|
| **Reqs** | int | 请求总数 |**Yes**|
| **ClientErr** | int | 客户端错误数 |**Yes**|
| **ServerErr** | int | 服务端错误数 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=StatWafReqsTrend
&Extent=org-xxx
&BeginTime=1586231349
&EndTime=1586231408
&Domain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "StatWafReqsTrendResponse",
  "Result": {
    "Count": 61,
    "Detail": [
      {
        "ClientErr": 0,
        "Reqs": 11,
        "ServerErr": 0,
        "Timestamp": 1586231350
      }
    ],
    "Type": "Reqs"
  },
  "RetCode": 0
}
```





