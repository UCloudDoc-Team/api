# 获取每日消费时长信息（仅含音视频数据） - GetURtcDaliyConsumption

## 简介

查询消费时长日详情，(根据起始日期和结束日期查询appid的日消费详情，详情包括音频，标清，高清，超高清，注解默认传入的时间戳参数，后端处理截取到日，查询间隔最大为180天）









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetURtcDaliyConsumption`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 查询的AppId (不能为空) |**Yes**|
| **StartTime** | int | 开始时间(毫秒时间戳） |**Yes**|
| **EndTime** | int | 结束时间(毫秒时间戳） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | [*AppTConsumption*](#AppTConsumption) | 类型参见AppTConsumption，对应的appid每日消费时长详情，包含音频消费时长数组，标清，高清，超高清的消费时长数组，数组中具体值的内容参见DailyConsumptionData |**Yes**|

#### 数据模型


#### AppTConsumption

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | AppId（项目id） |No|
| **Audio** | array[[*DailyConsumptionData*](#DailyConsumptionData)] | 音频消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData  |No|
| **SdVideo** | array[[*DailyConsumptionData*](#DailyConsumptionData)] | 标清消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData  |No|
| **HdVideo** | array[[*DailyConsumptionData*](#DailyConsumptionData)] | 高清消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData  |No|
| **FhdVideo** | array[[*DailyConsumptionData*](#DailyConsumptionData)] | 蓝光消费时长,数组类型，内含每日的具体数据，详情参见DailyConsumptionData  |No|

#### DailyConsumptionData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TimeStamp** | int | 时间戳(秒级) |No|
| **Value** | float | 具体的消费数值 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetURtcDaliyConsumption
&AppId=urtc-test
&StartTime=1536529440000
&EndTime=1536615840000
```

### 响应示例
    
```json
{
  "Action": "GetURtcDaliyConsumptionResponse",
  "Data": {
    "AppId": "urtc-test",
    "Audio": [
      {
        "TimeStamp": 1536624000,
        "Value": 12223
      },
      {
        "TimeStamp": 1536710400,
        "Value": 4567
      }
    ],
    "FhdVideo": [
      {
        "TimeStamp": 1536624000,
        "Value": 3333
      },
      {
        "TimeStamp": 1536710400,
        "Value": 2222
      }
    ],
    "HdVideo": [
      {
        "TimeStamp": 1536624000,
        "Value": 11111
      },
      {
        "TimeStamp": 1536710400,
        "Value": 33333
      }
    ],
    "SdVideo": [
      {
        "TimeStamp": 1536624000,
        "Value": 11111
      },
      {
        "TimeStamp": 1536710400,
        "Value": 33333
      }
    ],
    "UnitType": 1
  },
  "Msg": "NFNFfIWS",
  "RetCode": 0
}
```





