# 获取 kafka 实例 topic  列表信息 - ListUKafkaTopics

## 简介

获取 kafka 实例 topic  列表信息。实例ID，可以通过ListUKafkaInstance 接口的ClusterSet. ClusterInstanceId 获取






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ListUKafkaTopics)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ListUKafkaTopics`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目 ID。不填写为默认项目，子帐号必须填写。 请参考 [GetProjectList 接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterInstanceId** | string | 实例ID，可以通过ListUKafkaInstance 接口的ClusterSet. ClusterInstanceId 获取 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TopicList** | array[[*TopicInfo*](#TopicInfo)] | topic 信息列表 |**Yes**|
| **Length** | int | topic 列表长度 |No|

#### 数据模型


#### TopicInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Topic** | string | topic 名称 |No|
| **NumOfPartition** | int | 分区数量 |No|
| **NumOfOccupyBroker** | int | 占用 broker 数量 |No|
| **NumOfReplica** | int | 副本数量 |No|
| **UnderReplicasPer** | float | 落后副本占比 |No|
| **Status** | string | topic 状态 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ListUKafkaTopics
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=CYpWEvIo
&ClusterInstanceId=TKmEvKSR
```

### 响应示例
    
```json
{
  "Action": "ListUKafkaTopicsResponse",
  "Length": 5,
  "RetCode": 0,
  "TopicList": [
    {
      "NumOfOccupyBroker": 2,
      "NumOfPartition": 1,
      "NumOfReplica": 4,
      "Status": "NONE|INIT|DOING",
      "Topic": "xlqURVbE",
      "UnderReplicasPer": 5.63136
    }
  ]
}
```





