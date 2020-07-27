# 获取 topic 详细信息 - GetUKafkaTopicInfo

## 简介

获取指定 topic 的详细信息，包括Topic属性、消息动态、分区情况






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUKafkaTopicInfo)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUKafkaTopicInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **ClusterInstanceId** | string | Ukafka 集群 ID |**Yes**|
| **Topic** | string | 指定的 Topic |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Partitions** | object | topic 分区信息 |**Yes**|
| **TopicProperty** | [*TopicProperty*](#TopicProperty) | topic 属性 |**Yes**|
| **MessageState** | [*MessageState*](#MessageState) | topic 消息动态 |**Yes**|

#### 数据模型


#### TopicProperty

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **NumOfReplica** | int | 副本数量 |No|
| **NumOfPartition** | int | 分区数量 |No|
| **NumOfBroker** | int | broker 数量 |No|
| **NumOfOccupyBroker** | int | 占用 broker 数量 |No|
| **UnderReplicasPer** | float | 落后副本占比 |No|
| **BrokerSpreadPer** | float | topic 的 broker 覆盖率 |No|
| **BrokerSkewedPer** | float | topic 的 broker 倾斜率 |No|
| **PreferredReplicasPer** | float | 优先副本占有率 |No|
| **SumOfPartitionOffset** | int | topic 的 offset 之和 |No|
| **SumTopicUsage** | int | topic 的磁盘使用之和 |No|

#### MessageState

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **LastUpdateTime** | int | topic上次更新时间（时间戳） |No|
| **BytesInPerSec** | float | topic 每分钟流入消息速率 |No|
| **BytesOutPerSec** | float | topic 每分钟流出消息速率 |No|
| **MessagesInPerSec** | float | topic 每分钟流入消息条数 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUKafkaTopicInfo
&Zone=cn-bj2-02
&ClusterInstanceId=ukafka-asje3q
&Topic=foo
&Region=VjMeLUzs
&ProjectId=AQtYNwBR
```

### 响应示例
    
```json
{
  "Action": "GetUKafkaTopicInfoResponse",
  "MessageState": {
    "BytesInPerSec": 58.74732451878237,
    "BytesOutPerSec": 58.06401734087217,
    "LastUpdateTime": 1537340210000,
    "MessagesInPerSec": 1.2239025941412993
  },
  "Partitions": {
    "0": {
      "isr": [
        3,
        2,
        1
      ],
      "leader": 3,
      "partition": 0,
      "replicas": [
        3,
        2,
        1
      ],
      "topic": "foo",
      "usage": 190224
    },
    "1": {
      "isr": [
        1,
        3,
        2
      ],
      "leader": 1,
      "partition": 1,
      "replicas": [
        1,
        3,
        2
      ],
      "topic": "foo",
      "usage": 190672
    },
    "2": {
      "isr": [
        2,
        1,
        3
      ],
      "leader": 2,
      "partition": 2,
      "replicas": [
        2,
        1,
        3
      ],
      "topic": "foo",
      "usage": 190372
    }
  },
  "RetCode": 0,
  "TopicProperty": {
    "BrokerSkewedPer": 0,
    "BrokerSpreadPer": 1,
    "PreferredReplicasPer": 1,
    "SumOfPartitionOffset": 1773815,
    "SumTopicUsage": 571268,
    "numOfBroker": 3,
    "numOfOccupyBroker": 3,
    "numOfPartition": 3,
    "numOfReplica": 3,
    "underReplicasPer": 0
  }
}
```





