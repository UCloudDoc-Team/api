# 根据 Topic 和时间查询 Message 列表 - QueryURocketMQMessageByTopic

## 简介

根据 Topic 查询某个时间范围内的消息, 默认最大3天范围. 根据 Topic 查询 Message 时, 不返回 `MessageBody`.









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryURocketMQMessageByTopic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Begin** | int | 开始时间 Unix 秒 |**Yes**|
| **End** | int | 结束时间 |**Yes**|
| **TopicName** | string | Topic 名称 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **MessageList** | array[[*MessageBaseInfo*](#MessageBaseInfo)] | message列表 |No|

#### 数据模型


#### MessageBaseInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Properties** | [*MessageProperties*](#MessageProperties) | Message属性 |No|
| **MsgId** | string | MessageID |No|
| **Topic** | string | Topic名称 |No|
| **StoreTimestamp** | int | 保存时间戳 |No|

#### MessageProperties

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **TAGS** | string | Message 的 Tag |**Yes**|
| **KEYS** | string | Message 的 Key |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryURocketMQMessageByTopic
&Region=cn-zj
&ProjectId=LRsgyvbM
&ServiceId=aUMFIPvT
&TopicId=geZjcTRm
&Begin=6
&End=6
```

### 响应示例
    
```json
{
  "Action": "QueryURocketMQMessageByTopicResponse",
  "Message": "ouPqwKpk",
  "MessageList": [
    {
      "MsgId": "yBMTthbf",
      "Properties": "lUCCvlZf",
      "StoreTimestamp": 6,
      "Topic": "YYsBgRvA"
    }
  ],
  "RetCode": 0
}
```





