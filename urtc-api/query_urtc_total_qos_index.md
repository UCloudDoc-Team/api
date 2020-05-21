# 查询总的QOS质量指标(上行总码率，下行总码率，卡顿) - QueryURtcTotalQosIndex

## 简介

查询总的QOS质量指标(上行总码率，下行总码率，卡顿)








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcTotalQosIndex`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 待查询的应用id |**Yes**|
| **RoomId** | string | 	<br />待查询的房间名 |**Yes**|
| **QueryUser** | string | 待查询的用户名 |**Yes**|
| **StartTime** | int | 秒时间戳 |**Yes**|
| **EndTime** | int | 秒时间戳 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | [*TotalQosIndex*](#TotalQosIndex) | 参见TotalQosIndex |**Yes**|

#### 数据模型


#### TotalQosIndex

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TupBitrate** | array[[*QosItem*](#QosItem)] | 上行总码率 |**Yes**|
| **TdownBitrate** | array[[*QosItem*](#QosItem)] | 下行总码率 |**Yes**|
| **TlostFrame** | array[[*QosItem*](#QosItem)] | 卡顿指标 |**Yes**|

#### QosItem

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间 |**Yes**|
| **Value** | string | 数值 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcTotalQosIndex
&AppId='URtc-h4r1txxy'
&RoomId='8000'
&QueryUser='123'
&StartTime=1571204961
&EndTime=1571205961
```

### 响应示例
    
```json
{
  "Action": "QueryURtcTotalQosIndexResponse",
  "Data": {
    "TdownBitrate": [
      {
        "Time": 1571204961,
        "Value": 231
      },
      {
        "Time": 1571204991,
        "Value": 222
      }
    ],
    "TlostFrame": [
      {
        "Time": 1571204961,
        "Value": 231
      },
      {
        "Time": 1571204991,
        "Value": 222
      }
    ],
    "TupBitrate": [
      {
        "Time": 1571204961,
        "Value": 231
      },
      {
        "Time": 1571204991,
        "Value": 222
      }
    ]
  },
  "Msg": "Succeed",
  "RetCode": 0
}
```





