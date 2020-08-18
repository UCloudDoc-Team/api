# 根据CallId获取流信息（最大连麦人数&连麦列表） - DescribeURtcStreamByCallId

## 简介

根据CallId获取流信息（最大连麦人数&连麦列表）








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeURtcStreamByCallId`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 查询的AppId |**Yes**|
| **CallId** | string | 查询的CallId (每次通话记录Id,从QueryURtcOnlineUsers获取) |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MaxPublishCount** | int | 当前CallId最大连麦人数 |**Yes**|
| **Data** | [*DescribeURTCStreamByCallIdData*](#DescribeURTCStreamByCallIdData) | 当前CallId连麦列表信息 |**Yes**|

#### 数据模型


#### DescribeURTCStreamByCallIdData

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **EndTime** | int | 连麦结束时间 |No|
| **StartTime** | int | 连麦开始时间 |No|
| **UserId** | string | 连麦用户 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeURtcStreamByCallId
&CallId=ruygwRZC
&AppId=KEyFDRjM
&Offset=3
&Limit=6
```

### 响应示例
    
```json
{
  "Data": [
    {
      "EndTime": 1594978290,
      "StartTime": 1594978353,
      "UserId": "698i5ww5"
    },
    {
      "EndTime": 1594978191,
      "StartTime": 1594978354,
      "UserId": "b3tlj9ka"
    },
    {
      "EndTime": 1594978356,
      "StartTime": 1594978360,
      "UserId": "f69gtx9v"
    },
    {
      "EndTime": 1594978184,
      "StartTime": 1594978355,
      "UserId": "po6wxkfs"
    }
  ],
  "MaxPublishCount": 4,
  "RetCode": 0,
  "RoomId": "dsdjddjskjdksksdjjk"
}
```





