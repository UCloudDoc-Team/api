# 查询空间-DescribeUMemSpace

获取UMem内存空间列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|返回数据长度, 默认为20|No|
|SpaceId|string|内存空间ID (无ID，则获取所有)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|JSON 格式的UMem内存空间实例列表, 详细参见 UMemSpaceSet|No|
|TotalCount|int|根据过滤条件得到的总数|No|

## UMemSpaceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区，参见[可用区列表](../summary/regionlist.html)|No|
|Tag|string||**Yes**|
|RewriteTime|int|运维时间0   //0点1   //1点依次类推|**Yes**|
|SpaceId|string|内存空间ID|No|
|SubnetId|string||No|
|VPCId|string||No|
|Name|string|内存空间名称|No|
|CreateTime|int|创建时间|No|
|ExpireTime|int|到期时间|No|
|Type|string|空间类型:single(无热备),double(热备)|No|
|Protocol|string|协议类型: memcache, redis|No|
|Size|int|容量单位GB|No|
|UsedSize|int|使用量单位MB|No|
|State|string|Starting:创建中 Running:运行中 Fail:失败|No|
|ChargeType|string|Year, Month, Dynamic, Trial|No|
|Address|array|IP端口信息请参见 UMemSpaceAddressSet|No|

## UMemSpaceAddressSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string|UMem实例访问IP|No|
|Port|int|UMem实例访问Port|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemSpace
&Region=cn-bj2

```

# Response Example
```
{
    "Action": "DescribeUMemSpaceResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DataSet": [
        {
            "VPCId": "uvnet-XXXXXX4j", 
            "Protocol": "memcache", 
            "Name": "fbs_XXXX", 
            "Zone": "cn-bj2-04", 
            "UsedSize": 0, 
            "SpaceId": "umem-m3XXXXXX3", 
            "ExpireTime": 1530374400, 
            "State": "Running", 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "Address": [
                {
                    "IP": "XX.19X.1XX.4XX", 
                    "Port": 11211
                }
            ], 
            "SubnetId": "subnet-iiXXXXz", 
            "Type": "double", 
            "CreateTime": 1529894002, 
            "Size": 8
        }
    ]
}
```

