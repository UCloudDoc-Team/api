# 获取热点referer统计 - GetNewUcdnLogRefererStatistics

## 简介

获取热点referer统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetNewUcdnLogRefererStatistics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetNewUcdnLogRefererStatistics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **DomainId** | string | 域名id，创建域名时生成的id |No|
| **Areacode** | string | 查询带宽区域 cn代表国内 abroad代表海外 ；目前只支持国内 |No|
| **BeginTime** | int | 查询带宽的起始时间，格式：时间戳 |No|
| **EndTime** | int | 查询统计日志的结束时间，格式：时间戳。最大时间间隔30天 |No|
| **OrderBy** | int | 0表示按流量降序排列，1表示按照下载次数降序排列，默认为0 |No|
| **Limit** | int | 返回的结果数量限制，默认1000 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RefererStatistics** | array[[*RefererStatistics*](#RefererStatistics)] | 按天统计实例 |No|

#### 数据模型


#### RefererStatistics

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Date** | string | 日期 |No|
| **RefererList** | array[[*RefererList*](#RefererList)] | Referer实例表 |No|

#### RefererList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Referer** | string | 客户端请求的referer |No|
| **RequestTimes** | int | 次数 |No|
| **Percent** | float | 次数占比，单位% |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetNewUcdnLogRefererStatistics
&DomainId=test.com
&Areacode=cn
&BeginTime=1620057600
&EndTime=1620069600
&OrderBy=1
&Limit=100
```

### 响应示例
    
```json
{
  "Action": "GetNewUcdnLogRefererStatisticsResponse",
  "RefererStatistics": [
    {
      "Date": "gBcvvycW",
      "RefererList": [
        {
          "Percent": 1.77674,
          "Referer": "VSfcMdFp",
          "RequestTimes": 5
        }
      ]
    }
  ],
  "RetCode": 0
}
```





