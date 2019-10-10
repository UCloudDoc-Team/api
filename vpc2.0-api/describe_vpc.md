# 获取VPC信息-DescribeVPC

获取VPC信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|VPCIds.n|string|VPCId|No|
|Tag|string|业务组名称|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|vpc信息，具体结构见下方VPCInfo|No|

## VPCInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NetworkInfo|array||**Yes**|
|SubnetCount|int||**Yes**|
|CreateTime|int||**Yes**|
|UpdateTime|int||**Yes**|
|Tag|string||**Yes**|
|Name|string||**Yes**|
|VPCId|string|VPCId|No|
|Network|array||No|
|IPv6Network|string|VPC关联的IPv6网段|No|
|OperatorName|string|VPC关联的IPv6网段所属运营商|No|

## VPCNetworkInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Network|string|vpc地址空间|No|
|SubnetCount|int|地址空间中子网数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeVPC
&ProjectId=org-xxx
&Region=cn-sh2
&VPCIds.0=uvnet-xxx
```

# Response Example
```
{
    "Action": "DescribeVPCResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "UpdateTime": 1514313728, 
            "VPCId": "uvnet-xxx", 
            "Network": [
                "10.44.x.0/16"
            ], 
            "NetworkInfo": [
                {
                    "Network": "10.44.x.0/16", 
                    "SubnetCount": 1
                }
            ], 
            "Tag": "Default", 
            "SubnetCount": 1, 
            "CreateTime": 1514313728, 
            "Name": "DefaultVPC"
        }, 
        {
            "Remark": "", 
            "VPCId": "uvnet-xxxxx", 
            "Network": [
                "192.168.x.0/16", 
                "10.0.0.0/8"
            ], 
            "NetworkInfo": [
                {
                    "Network": "192.168.x.0/16", 
                    "SubnetCount": 1
                }, 
                {
                    "Network": "10.0.0.0/8", 
                    "SubnetCount": 1
                }
            ], 
            "UpdateTime": 1533891438, 
            "Tag": "Default", 
            "SubnetCount": 2, 
            "CreateTime": 1533891436, 
            "Name": "testabc"
        }
    ]
}
```

