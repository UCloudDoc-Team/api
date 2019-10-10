# 列出 kafka 集群 topic  -ListUKafkaTopics

展示kafka集群上所有topic

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目 ID。不填写为默认项目，子帐号必须填写。 请参考 [GetProjectList 接口](api/summary/get_project_list)|No|
|ClusterInstanceId|string|集群资源id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TopicList|array|topic 信息列表|**Yes**|
|Length|int|列表长度|No|

## TopicInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Topic|string|topic 名称|No|
|NumOfPartition|int|分区数量|No|
|NumOfOccupyBroker|int|占用 broker 数量|No|
|NumOfReplica|int|副本数量|No|
|UnderReplicasPer|float|落后副本占比|No|
|Status|string|topic 状态|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListUKafkaTopics
&Zone=cn-zj-02
&ClusterInstanceId=ukafka-asje3q
&Region=cn-zj
&ProjectId=qVHhqxTv
```

# Response Example
```
{
    "Action": "ListTopicsResponse", 
    "Length": 3, 
    "TopicList": [
        {
            "allReplicas": 9, 
            "topic": "nil", 
            "numOfPartition": 3, 
            "underReplicasPer": 0, 
            "allIsr": 9, 
            "numOfReplica": 3, 
            "numOfOccupyBroker": 3
        }, 
        {
            "allReplicas": 9, 
            "topic": "foo", 
            "numOfPartition": 3, 
            "underReplicasPer": 0, 
            "allIsr": 9, 
            "numOfReplica": 3, 
            "numOfOccupyBroker": 3
        }, 
        {
            "allReplicas": 3, 
            "topic": "bar", 
            "numOfPartition": 1, 
            "underReplicasPer": 0, 
            "allIsr": 3, 
            "numOfReplica": 3, 
            "numOfOccupyBroker": 3
        }
    ], 
    "RetCode": 0
}
```

