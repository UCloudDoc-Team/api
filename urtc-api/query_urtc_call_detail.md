# 查用用户通话时长清单 - QueryURtcCallDetail

## 简介

查用用户通话时长清单








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURtcCallDetail`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AppId** | int | 待查询的应用id |**Yes**|
| **RoomId** | string | 	<br />待查询的房间名 |**Yes**|
| **QueryUser** | string | 待查询的用户名 |**Yes**|
| **StartTime** | int | 查询开始时间（秒级） |**Yes**|
| **EndTime** | int | 查询结束时间（秒级） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Msg** | string | RetCode为0时返回succed,不为0返回具体的错误消息提示内容 |**Yes**|
| **Data** | array[string] | 数组元素参见（UserCallInfo） |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURtcCallDetail
&AppId=URtc-h4r1txxy
&RoomId=222
&QueryUser=200001124
&StartTime=4
&EndTime=1
```

### 响应示例
    
```json
{
  "Action": "QueryURtcCallDetailResponse",
  "Data": [
    {
      "Time": 1570686340,
      "TimeType": 1,
      "UserId": "200001124"
    }
  ],
  "Msg": "Succed",
  "RetCode": 0
}
```





