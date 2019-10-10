# 列出 Kafka 消费组-ListUKafkaConsumers

列出 Kafka 消费组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目 ID。不填写为默认项目，子帐号必须填写。 请参考 [GetProjectList 接口](api/summary/get_project_list)|No|
|ClusterInstanceId|string|Kafka 集群 ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Groups|array|消费者组列表|No|

## Group
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GroupName|string|消费者组组名|No|
|Type|string|消费者组类型|No|
|NumOfTopics|int|订阅 Topic 数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListUKafkaConsumers
&Region=befZCCUI
&Zone=boqlDiIv
&ProjectId=aTyyvWoG
&ClusterInstanceId=yUHbmMXE
&ConsumerGroup=LgcijwcM
&Type=ZK
```

# Response Example
```
{
    "Action": "ListUKafkaConsumersResponse", 
    "RetCode": 0, 
    "Groups": [
        {
            "NumOfTopics": 1, 
            "GroupName": "your_group", 
            "Type": "ZK"
        }, 
        {
            "NumOfTopics": 2, 
            "GroupName": "group1", 
            "Type": "ZK"
        }, 
        {
            "NumOfTopics": 1, 
            "GroupName": "console-consumer-15031", 
            "Type": "KF"
        }, 
        {
            "NumOfTopics": 7, 
            "GroupName": "c-group-no.1", 
            "Type": "KF"
        }, 
        {
            "NumOfTopics": 1, 
            "GroupName": "console-consumer-49808", 
            "Type": "KF"
        }, 
        {
            "NumOfTopics": 7, 
            "GroupName": "console-consumer-66549", 
            "Type": "KF"
        }, 
        {
            "NumOfTopics": 1, 
            "GroupName": "console-consumer-27520", 
            "Type": "KF"
        }, 
        {
            "NumOfTopics": 1, 
            "GroupName": "console-consumer-6519", 
            "Type": "KF"
        }
    ]
}
```

