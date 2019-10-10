# 获取VPC互通信息-DescribeVPCIntercom

获取VPC互通信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|源VPC所在地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|源VPC所在项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VPCId|string|VPC短ID|**Yes**|
|DstRegion|string|目的VPC所在地域，默认为全部地域|No|
|DstProjectId|string|目的项目ID，默认为全部项目|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|联通VPC信息数组|No|

## VPCIntercomInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目Id|No|
|Network|array|VPC的地址空间|No|
|DstRegion|string|所属地域|No|
|Name|string|VPC名字|No|
|VPCId|string|VPCId|No|
|Tag|string|业务组（未分组显示为 Default）|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeVPCIntercom
&Region=cn-sh2
&ProjectId=org-XXX
&VPCId=uvnet-XXXX
```

# Response Example
```
{
    "Action": "DescribeVPCIntercomResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "VPCId": "uvnet-XXXXX", 
            "Name": "DefaultVPC", 
            "ProjectId": "org-XXXXX", 
            "Tag": "Default", 
            "DstRegion": "ge-fra", 
            "Network": [
                "10.29.XX.0/16"
            ]
        }, 
        {
            "Remark": "", 
            "VPCId": "uvnet-XXXX", 
            "Name": "ulb-vpc", 
            "ProjectId": "org-XXX", 
            "Tag": "Default", 
            "DstRegion": "cn-sh2", 
            "Network": [
                "172.16.XX.0/12", 
                "10.1.XX.0/16"
            ]
        }
    ]
}
```

