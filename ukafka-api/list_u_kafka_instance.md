# 列举集群信息-ListUKafkaInstance

列举集群信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Limit|string|默认为60|No|
|Offset|string|默认为0|No|
|Filter|string|是否过滤删除了的节点，默认为‘true’|No|
|VPCId|string|VPCId|No|
|SubnetId|string|SubnetId|No|
|BusinessId|string|BusinessId|No|
|ClusterInstanceId|string|集群ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ClusterSet|string|信息|**Yes**|
|TotalCount|string|总数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ListUKafkaInstance
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=psLewFbM
&Limit=LidCsVTz
&Offset=Rtvvkzbo
&Filter=xaSWuIxd
&VPCId=JiyiuaGj
&SubnetId=lpUAUCTy
&BusinessId=HttFFiEn
&ClusterInstanceId=bfibtMTE
```

# Response Example
```
{
    "Action": "ListUKafkaInstanceResponse", 
    "TotalCount": 1, 
    "ClusterSet": [
        {
            "Remark": "", 
            "VPCId": "uvnet-rgi3ym", 
            "NewMessage": "Yes", 
            "Zone": "cn-bj2-02", 
            "RunningTime": 5623, 
            "ClusterInstanceName": "test", 
            "BusinessId": "", 
            "State": "Running", 
            "ExpireTime": 1551369600, 
            "Framework": "Kafka", 
            "RedundantCount": 0, 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "AutoRenew": "Yes", 
            "ClusterInstanceId": "ukafka-5xagjz", 
            "UHostCount": 3, 
            "SubnetId": "subnet-ah4q5l", 
            "FrameworkVersion": "1.1.1", 
            "CreateTime": 1550476133
        }
    ], 
    "RetCode": 0
}
```

