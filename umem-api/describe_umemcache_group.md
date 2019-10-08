# 显示Memcache-DescribeUMemcacheGroup

显示Memcache

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|GroupId|string|组的ID,如果指定则获取描述，否则为列表操 作,需指定Offset/Limit|No|
|Offset|int|分页显示的起始偏移, 默认值为0|No|
|Limit|int|分页显示的条目数, 默认值为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|组的总的节点个数|No|
|DataSet|array|组列表,参见 UMemcacheGroupSet|No|

## UMemcacheGroupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GroupId|string|组ID|No|
|Name|string|组名称|No|
|ConfigId|string|节点的配置ID|No|
|VirtualIP|string|节点的虚拟IP地址|No|
|Port|int|节点分配的服务端口|No|
|Size|int|容量单位GB|No|
|UsedSize|int|使用量单位MB|No|
|Version|string|Memcache版本信息,默认为1.4.31|No|
|State|string|状态标记 Creating // 初始化中 CreateFail // 创建失败 Deleting // 删除中 DeleteFail // 删除失败 Running // 运行 Resizing // 容量调整中 ResizeFail // 容量调整失败 Configing // 配置中 ConfigFail // 配置失败Restarting // 重启中|No|
|CreateTime|int|创建时间 (UNIX时间戳)|No|
|ModifyTime|int|修改时间 (UNIX时间戳)|No|
|ExpireTime|int|过期时间 (UNIX时间戳)|No|
|ChargeType|string|计费类型:Year,Month,Dynamic 默认Dynamic|No|
|Tag|string|业务组名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemcacheGroup
&Region=cn-east-01
&GroupId=umemcache-00f986
&Offset=0
&Limit=20
&Tag=Default
```

# Response Example
```
{
    "Action": "DescribeUMemcacheGroupResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Version": "1.4.33", 
            "Name": "test1233", 
            "Port": 11211, 
            "UsedSize": 0, 
            "VirtualIP": "x.xx.x.x", 
            "ExpireTime": 12345, 
            "State": "Running", 
            "Tag": "Default", 
            "ChargeType": "Month", 
            "ModifyTime": 1522222, 
            "ConfigId": "9a891891-c245-4b66-bcexxxxxxxxx", 
            "GroupId": "umemcache-xxxxx", 
            "CreateTime": 1522222, 
            "Size": 2
        }
    ]
}
```

