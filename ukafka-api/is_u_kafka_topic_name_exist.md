# 检查topic名称是否已存在-IsUKafkaTopicNameExist

检查一个topic名称是否已经在集群中了

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ClusterInstanceId|string|集群ID|**Yes**|
|TopicName|string|待检查的topic名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|IsExist|string|是否已经存在|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=IsUKafkaTopicNameExist
&Region=cn-zj
&Zone=cn-zj-01
&ClusterInstanceId=ONbxfJxK
&TopicName=vtsRCkBK
```

# Response Example
```
{
    "Action": "IsUKafkaTopicNameExistResponse", 
    "RetCode": 0, 
    "IsExist": "KDuPjTLR"
}
```

