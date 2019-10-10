# 获取内网虚拟IP信息-DescribeVIP

获取内网VIP详细信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|VPCId|string|vpc的id,指定SubnetId时必填|No|
|SubnetId|string|子网id，不指定则获取VPCId下的所有vip|No|
|Tag|string|业务组名称, 默认为 Default|No|
|BusinessId|string|业务组|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VIPSet|array|内网VIP详情，请见VIPDetailSet|No|
|DataSet|array|内网VIP地址列表|No|
|TotalCount|int|vip数量|No|

## VIPDetailSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|地域|No|
|VIPId|string|虚拟ip id|No|
|CreateTime|int|创建时间|No|
|RealIp|string|真实主机ip|No|
|VIP|string|虚拟ip|No|
|SubnetId|string|子网id|No|
|VPCId|string|VPC id|No|
|Name|string|VIP名称|No|
|Remark|string|VIP备注|No|
|Tag|string|VIP所属业务组|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeVIP
&Region=cn-bj2
&ProjectId=org-xxx
&Zone=cn-bj2-04
&VPCId=vnet-xxx
```

# Response Example
```
{
    "Action": "DescribeVIPResponse", 
    "TotalCount": 1, 
    "VIPSet": [
        {
            "Remark": "Default", 
            "VPCId": "uvnet-XXX", 
            "Name": "VIP", 
            "Zone": "cn-sh2-01", 
            "VIPId": "vip-XXX", 
            "VIP": "10.25.XX.XX", 
            "Tag": "Default", 
            "SubnetId": "subnet-XXX", 
            "RealIp": "", 
            "CreateTime": 1521970238
        }
    ], 
    "RetCode": 0, 
    "DataSet": [
        "10.25.XX.XX"
    ]
}
```

