# 获取 Kafka 消费组信息-DescribeUKafkaConsumer

获取 Kafka 消费组信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目 ID。不填写为默认项目，子帐号必须填写。 请参考 [GetProjectList 接口](../summary/get_project_list.html)|No|
|ClusterInstanceId|string|Kafka 集群 ID|**Yes**|
|ConsumerGroup|string|消费组组名|**Yes**|
|Type|string|消费者组类型（同消费者组列表返回的类型值）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupName|string|消费者组组名|No|
|Type|string|消费者组类型|No|
|Topics|string|消费者组所订阅 topic 信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUKafkaConsumer
&Region=cn-bj2
&Zone=cn-bj2-02
&ProjectId=KQFUAJET
&ClusterInstanceId=ukafka-asje3q
&ConsumerGroup=group1
&Type=ZK
```

# Response Example
```
{
    "Action": "DescribeUKafkaConsumerResponse", 
    "GroupName": "group1", 
    "Topics": {
        "foo": {
            "LastUpdateTime": 1538194238000.0, 
            "PartitionAssignedPer": 1, 
            "LogPer": 1.3680915448685166e-05, 
            "TotalLag": 63, 
            "Partitions": {
                "1": {
                    "LogEndOffset": 1534529, 
                    "CurrentOffset": 1534519, 
                    "Consumer": "group1_ukafka-asje3q-kafka2-1538101885995-a9d3def3-0", 
                    "Lag": 10
                }, 
                "0": {
                    "LogEndOffset": 1534867, 
                    "CurrentOffset": 1534824, 
                    "Consumer": "group1_ukafka-asje3q-kafka2-1538033810949-626a2e06-0", 
                    "Lag": 43
                }, 
                "2": {
                    "LogEndOffset": 1535559, 
                    "CurrentOffset": 1535549, 
                    "Consumer": "group1_ukafka-asje3q-kafka2-1538101889777-b0fb1091-0", 
                    "Lag": 10
                }
            }
        }, 
        "bar": {
            "PartitionAssignedPer": 0, 
            "LagPer": 0.2941239495259584, 
            "LastUpdateTime": 1538194238000.0, 
            "TotalLag": 837280, 
            "Partitions": {
                "0": {
                    "LogEndOffset": 2846691, 
                    "CurrentOffset": 2009411, 
                    "Consumer": "", 
                    "Lag": 837280
                }
            }
        }
    }, 
    "Type": "ZK", 
    "RetCode": 0
}
```

