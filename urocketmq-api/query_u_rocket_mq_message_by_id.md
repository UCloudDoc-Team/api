# 根据 ID 查询 Message 详情 - QueryURocketMQMessageByID

## 简介

获取一个指定 ID 的 Message 的详情









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURocketMQMessageByID`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **MsgId** | string | Message ID |**Yes**|
| **TopicName** | string | Topic 名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MessageList** | array[[*MessageDetail*](#MessageDetail)] | message详细信息 |No|

#### 数据模型


#### MessageDetail

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Properties** | [*MessageProperties*](#MessageProperties) | Message属性 |**Yes**|
| **Topic** | string | Topic名称 |**Yes**|
| **MsgId** | string | Message 的 ID |**Yes**|
| **StoreTimestamp** | int | Message 的落盘时间, Unix 毫秒 |**Yes**|
| **MessageBody** | string | Message 的 Body |**Yes**|

#### MessageProperties

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TAGS** | string | Message 的 Tag |**Yes**|
| **KEYS** | string | Message 的 Key |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURocketMQMessageByID
&Region=cn-zj
&ProjectId=TbKkMNBW
&ServiceId=lDRInGeU
&GroupName=OpqwDJnj
&MsgId=BIWmWMwr
```

### 响应示例
    
```json
{
  "Action": "QueryURocketMQMessageByIDResponse",
  "Message": "XNnTsUzD",
  "MessageList": [
    {
      "MessageBody": "dtPXPyXq",
      "MsgId": "mTpiCAmy",
      "Properties": {},
      "StoreTimestamp": 4,
      "Topic": "fwiLfLtZ"
    }
  ],
  "RetCode": 0
}
```





