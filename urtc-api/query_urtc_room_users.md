# 查询房间列用户列表信息 - QueryURtcRoomUsers

## 简介

查询房间列用户列表信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcRoomUsers`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | string | 	<br />查询的AppId (不能为空) |**Yes**|
| **RoomId** | string | 查询的房间id(不能为空) |**Yes**|
| **StartTime** | int | 待查询开始时间 |**Yes**|
| **EndTime** | int | 待查询结束时间 |**Yes**|
| **Offset** | int | 列表起始位置偏移量，默认为0<br /> |No|
| **Limit** | int | 返回数据长度，默认为20，最大100<br /> |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | array[[*RoomUsersInfo*](#RoomUsersInfo)] | 用户信息列表（数组元素查看RoomUsersInfo） |**Yes**|
| **TotalCount** | int | 房间总人数 |No|

#### 数据模型


#### RoomUsersInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 区域 |**Yes**|
| **UserId** | string | 用户ID |**Yes**|
| **LastEnterTime** | int | 最后一次进入房间时间 |**Yes**|
| **LastLeaveTime** | int | 最后一次离开房间时间，未离开返回0 |**Yes**|
| **Sdkv** | string | sdk版本 |**Yes**|
| **Device** | string | 设备名称 |**Yes**|
| **System** | string | 系统类型 |**Yes**|
| **Network** | string | 网络类型 |**Yes**|
| **FirstEnterTime** | int | 最早一次进入房间时间 |**Yes**|
| **Available** | boolean | 设备可用性 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcRoomUsers
&AppId=URtc-h4r1txxy
&RoomId=2800
&StartTime=6
&EndTime=3
&Offset=4
&Limit=1
```

### 响应示例
    
```json
{
  "Action": "QueryURtcRoomUsersResponse",
  "Data": [
    {
      "Device": "HUAWEI_DUK-AL20_HUAWEIDUK-AL20",
      "LastEnterTime": 1570677340,
      "LastLeaveTime": 1570677860,
      "Network": "4g",
      "Region": "长沙",
      "Sdkv": "1.4.3",
      "System": "android9arm64-v8a",
      "UserId": "atgPMSIG"
    }
  ],
  "Msg": "dvDadUvN",
  "RetCode": 0,
  "TotalCount": 4
}
```





