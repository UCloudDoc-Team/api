# 获取 topic 详细信息-GetUKafkaTopicInfo

获取指定 topic 的详细信息，包括Topic属性、消息动态、分区情况

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ClusterInstanceId|string|Ukafka 集群 ID|**Yes**|
|Topic|string|指定的 Topic|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Partitions|object|topic 分区信息|**Yes**|
|TopicProperty|object|topic 属性|**Yes**|
|MessageState|object|topic 消息动态|**Yes**|

## TopicProperty
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NumOfReplica|int|副本数量|No|
|NumOfPartition|int|分区数量|No|
|NumOfBroker|int|broker 数量|No|
|NumOfOccupyBroker|int|占用 broker 数量|No|
|UnderReplicasPer|float|落后副本占比|No|
|BrokerSpreadPer|float|topic 的 broker 覆盖率|No|
|BrokerSkewedPer|float|topic 的 broker 倾斜率|No|
|PreferredReplicasPer|float|优先副本占有率|No|
|SumOfPartitionOffset|int|topic 的 offset 之和|No|
|SumTopicUsage|int|topic 的磁盘使用之和|No|

## MessageState
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LastUpdateTime|int|topic上次更新时间（时间戳）|No|
|BytesInPerSec|float|topic 每分钟流入消息速率|No|
|BytesOutPerSec|float|topic 每分钟流出消息速率|No|
|MessagesInPerSec|float|topic 每分钟流入消息条数|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUKafkaTopicInfo
&Zone=cn-bj2-02
&ClusterInstanceId=ukafka-asje3q
&Topic=foo
&Region=VjMeLUzs
&ProjectId=AQtYNwBR
```

# Response Example
```
{
    "Action": "GetUKafkaTopicInfoResponse", 
    "TopicProperty": {
        "SumOfPartitionOffset": 1773815, 
        "BrokerSkewedPer": 0, 
        "PreferredReplicasPer": 1, 
        "SumTopicUsage": 571268, 
        "numOfBroker": 3, 
        "numOfPartition": 3, 
        "underReplicasPer": 0, 
        "numOfReplica": 3, 
        "numOfOccupyBroker": 3, 
        "BrokerSpreadPer": 1
    }, 
    "MessageState": {
        "MessagesInPerSec": 1.2239025941412993, 
        "BytesInPerSec": 58.74732451878237, 
        "LastUpdateTime": 1537340210000.0, 
        "BytesOutPerSec": 58.06401734087217
    }, 
    "RetCode": 0, 
    "Partitions": {
        "1": {
            "replicas": [
                1, 
                3, 
                2
            ], 
            "isr": [
                1, 
                3, 
                2
            ], 
            "partition": 1, 
            "topic": "foo", 
            "usage": 190672, 
            "leader": 1
        }, 
        "0": {
            "replicas": [
                3, 
                2, 
                1
            ], 
            "isr": [
                3, 
                2, 
                1
            ], 
            "partition": 0, 
            "topic": "foo", 
            "usage": 190224, 
            "leader": 3
        }, 
        "2": {
            "replicas": [
                2, 
                1, 
                3
            ], 
            "isr": [
                2, 
                1, 
                3
            ], 
            "partition": 2, 
            "topic": "foo", 
            "usage": 190372, 
            "leader": 2
        }
    }
}
```

