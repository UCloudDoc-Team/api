# 查询用户的事件列表 - QueryURtcUserEvent

## 简介

查询用户的事件列表









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcUserEvent`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 应用id |**Yes**|
| **RoomId** | string | 房间ID |**Yes**|
| **QueryUser** | string | 用户名 |**Yes**|
| **StartTime** | int | 开始时间 |**Yes**|
| **EndTime** | int | 结束时间 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | array[[*UsersEvent*](#UsersEvent)] | 用户信息列表（数组元素查看UsersEvent） |**Yes**|

#### 数据模型


#### UsersEvent

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **UserId** | string | 用户ID |**Yes**|
| **Time** | int | 时间戳 |**Yes**|
| **EventType** | int | 操作事件类型 (1.加入房间, 2.离开房间, 3.开始推流, 4.结束推流, 5.开始拉流, 6.结束拉流, 7.打开摄像头, 8.关闭摄像头, 9.打开麦克风, 10.关闭麦克风, 11.开启录制, 12.结束录制, 13.开启转推, 14.结束转推, 15.录制转推更新, 16.切换分辨率)<br />异常事件类型 (101.推流失败, 102.拉流失败, 103.获取摄像头失败, 104.获取麦克风失败, 105.获取扬声器失败, 106.CPU占用率高, 107.高丢包, 108.高延迟, 109.录制转码失败, 110.录制存储失败, 114. 加入房间失败, 115.转推失败) |**Yes**|
| **Desc** | string | 事件描述 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcUserEvent
&AppId=URtc-h4r1txxy
&RoomId=2800
&QueryUser=android_69dd21e41b1b4f3fa4cc067a02cc04c5
&StartTime=8
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "QueryURtcUserEventResponse",
  "Data": [
    {
      "EventType": 1,
      "Time": 1570677340,
      "UserId": "android_69dd21e41b1b4f3fa4cc067a02cc04c5"
    }
  ],
  "Msg": "succed",
  "RetCode": 0
}
```





