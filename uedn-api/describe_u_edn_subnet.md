# 获取子网列表-DescribeUEdnSubnet

获取子网列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|IdcId|string|机房ID|No|
|SubnetId|string|子网ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SubnetList|array|子网信息列表|No|

## SubnetInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SubnetId|string|子网ID|**Yes**|
|SubnetName|string|子网名称|**Yes**|
|IdcId|string|机房ID|**Yes**|
|CIDR|string|子网cidr|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|Comment|string|备注|**Yes**|
|TotalIpCnt|int|总ip数|**Yes**|
|AvailableIPCnt|int|可用ip数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUEdnSubnet
&ProjectId=org-xxx
&IdcId=uedn-idc-xxx
&SubnetId=uedn-subnet-xxx
```

# Response Example
```
{
    "Action": "DescribeUEdnSubnetResponse", 
    "SubnetList": [
        {
            "Comment": "igfjPEzM", 
            "TotalIpCnt": 254, 
            "AvailableIPCnt": 253, 
            "SubnetName": "test-subnet", 
            "SubnetId": "uedn-subnet-xxx", 
            "CIDR": "10.10.9.0/24", 
            "IdcId": "uedn-idc-xxx", 
            "CreateTime": 1577762217
        }
    ], 
    "RetCode": 0
}
```

