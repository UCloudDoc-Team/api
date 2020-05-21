# 查询房间列表及房间累计用户，峰值用户，当前用户 - QueryURtcOnlineUsers

## 简介

查询此appid下指定时间段内房间列表及其累计用户，峰值用户，当前用户








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcOnlineUsers`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | AppId |**Yes**|
| **StartTime** | int | 开始时间(秒时间戳） |**Yes**|
| **EndTime** | int | 结束时间(秒时间戳） |**Yes**|
| **RoomId** | string | 房间ID |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，默认为20，最大100<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | array[[*RoomUsers*](#RoomUsers)] | 类型参见RoomUsers,具体包含房间ID和具体人数 |**Yes**|
| **TotalCount** | int | 房间列表总数 |No|

#### 数据模型


#### RoomUsers

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RoomId** | string | 房间id |**Yes**|
| **Num** | int | 在线人数 |**Yes**|
| **CurrentAmount** | int | 当前用户数量 |**Yes**|
| **PeekAmount** | int | 峰值用户数量 |**Yes**|
| **AccumulationAmount** | int | 累计用户数量 |**Yes**|
| **StartTime** | int | 房间开始时间 |**Yes**|
| **EndTime** | int | 房间结束时间 |**Yes**|
| **RoomStatus** | boolean | 房间状态,进行中:true,已结束:false |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcOnlineUsers
&AppId=URtc-h4r1txxy
&StartTime=1563150096
&EndTime=1563158718
&RoomId=oMMAvLDR
&Offset=4
&Limit=8
```

### 响应示例
    
```json
{
  "Action": "QueryURtcOnlineUsersResponse",
  "Data": [
    {
      "Num": 123,
      "RoomId": "111"
    }
  ],
  "Msg": "Succeed",
  "RetCode": 0,
  "TotalCount": 7
}
```





