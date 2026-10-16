# 获取 Topic 列表 - ListURocketMQTopic

## 简介

获取一个 RocketMQ 服务下的所有用户 Topic(不包括系统自动创建的, 例如 SYS开头的, RETRY开头的等)









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListURocketMQTopic`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **ServiceId** | string | Service ID |**Yes**|
| **Limit** | int | 最多返回的条目数量, (0, 1000], 默认 20 条 |No|
| **Offset** | int | 查询起始位置, [0, ∞) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TopicList** | array[[*TopicInfo*](#TopicInfo)] | Topic列表 |No|
| **TotalCount** | int | 记录总数 |No|

#### 数据模型


#### TopicInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Remark** | string | Topic 描述 |No|
| **CreateTime** | int | Topic 创建时间 |No|
| **MessageType** | string | 消息类型 |No|
| **TopicId** | string | Topic ID |No|
| **TopicName** | string | Topic 名称 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListURocketMQTopic
&Region=cn-zj
&ProjectId=akthviXK
&ServiceId=rbpuvTti
&Limit=3
&Offset=7
&Limit=6
&Offset=3
```

### 响应示例
    
```json
{
  "Action": "ListURocketMQTopicResponse",
  "Message": "gYCmYFYR",
  "RetCode": 0,
  "TopicList": [
    {
      "CreateTime": "Lqgjjmcf",
      "Id": "VpElLtWl",
      "MessageType": "Normal",
      "Name": "laCiRFpA",
      "Remark": "mZqnUdRb"
    }
  ],
  "TotalCount": 7
}
```





