# 获取 Kafka 消费组信息 - DescribeUKafkaConsumer

## 简介

获取 Kafka 消费组信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeUKafkaConsumer)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUKafkaConsumer`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **Zone** | string | 可用区。参见 [可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目 ID。不填写为默认项目，子帐号必须填写。 请参考 [GetProjectList 接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **ClusterInstanceId** | string | Kafka 集群 ID |**Yes**|
| **ConsumerGroup** | string | 消费组组名 |**Yes**|
| **Type** | string | 消费者组类型（同消费者组列表返回的类型值） |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **GroupName** | string | 消费者组组名 |No|
| **Type** | string | 消费者组类型 |No|
| **Topics** | string | 消费者组所订阅 topic 信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUKafkaConsumer
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=KQFUAJET
&ClusterInstanceId=ukafka-asje3q
&ConsumerGroup=group1
&Type=ZK
```

### 响应示例
    
```json
{
  "Action": "DescribeUKafkaConsumerResponse",
  "GroupName": "group1",
  "RetCode": 0,
  "Topics": {
    "bar": {
      "LagPer": 0.2941239495259584,
      "LastUpdateTime": 1538194238000,
      "PartitionAssignedPer": 0,
      "Partitions": {
        "0": {
          "Consumer": "",
          "CurrentOffset": 2009411,
          "Lag": 837280,
          "LogEndOffset": 2846691
        }
      },
      "TotalLag": 837280
    },
    "foo": {
      "LastUpdateTime": 1538194238000,
      "LogPer": 0.000013680915448685166,
      "PartitionAssignedPer": 1,
      "Partitions": {
        "0": {
          "Consumer": "group1_ukafka-asje3q-kafka2-1538033810949-626a2e06-0",
          "CurrentOffset": 1534824,
          "Lag": 43,
          "LogEndOffset": 1534867
        },
        "1": {
          "Consumer": "group1_ukafka-asje3q-kafka2-1538101885995-a9d3def3-0",
          "CurrentOffset": 1534519,
          "Lag": 10,
          "LogEndOffset": 1534529
        },
        "2": {
          "Consumer": "group1_ukafka-asje3q-kafka2-1538101889777-b0fb1091-0",
          "CurrentOffset": 1535549,
          "Lag": 10,
          "LogEndOffset": 1535559
        }
      },
      "TotalLag": 63
    }
  },
  "Type": "ZK"
}
```





