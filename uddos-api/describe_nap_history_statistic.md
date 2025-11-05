# 获取高防历史统计 - DescribeNapHistoryStatistic

## 简介

获取高防历史统计






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeNapHistoryStatistic)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeNapHistoryStatistic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |**Yes**|
| **BeginTime** | int | 开始时间，Unix时间戳 |**Yes**|
| **EndTime** | int | 结束时间，Unix时间戳 |**Yes**|
| **NapIP** | string | 高防IP |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认不限制 |No|
| **Accuracy** | int | 查询粒度。1.分钟粒度 2.小时粒度 3.天粒度 默认为2<br />1.分钟粒度，BeginTime开始时间是7天内，EndTime-BeginTime时间跨度最大是1小时<br />2.小时粒度，BeginTime开始时间是30天内，EndTime-BeginTime时间跨度最大是7天<br />3.天粒度，BeginTime开始时间是180天内，EndTime-BeginTime时间跨度最大是90天 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **NetStats** | array[[*NetStats*](#NetStats)] | 统计数据 |**Yes**|

#### 数据模型


#### NetStats

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Time** | int | Unix时间戳 |No|
| **Ingress** | [*NetStatEntry*](#NetStatEntry) | 入向NetStatEntry |No|
| **Egress** | [*NetStatEntry*](#NetStatEntry) | 出向NetStatEntry |No|
| **Drop** | [*NetStatEntry*](#NetStatEntry) | 丢弃NetStatEntry |No|

#### NetStatEntry

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Bps** | float | 流量，单位：Mbits |No|
| **Pps** | int | 包量，单位：pps |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeNapHistoryStatistic
&ResourceId=usecure_ghp-sqyoxRVq
&BeginTime=1604160000
&EndTime=1606665600
&NapIP=10.5.12.3
&Accuracy=3
```

### 响应示例
    
```json
{
  "Action": "DescribeNapHistoryStatisticResponse",
  "NetStats": [
    {
      "Drop": {
        "Bps": 0,
        "Pps": 0
      },
      "Egress": {
        "Bps": 1122,
        "Pps": 3
      },
      "Ingress": {
        "Bps": 1122,
        "Pps": 3
      },
      "Time": 1604160000
    },
    {
      "Drop": {
        "Bps": 0,
        "Pps": 0
      },
      "Egress": {
        "Bps": 3322,
        "Pps": 3
      },
      "Ingress": {
        "Bps": 3322,
        "Pps": 3
      },
      "Time": 1604246400
    }
  ],
  "RetCode": 0
}
```





