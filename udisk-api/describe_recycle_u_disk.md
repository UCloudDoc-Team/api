# 拉取回收站中云硬盘列表-DescribeRecycleUDisk

拉取回收站中云硬盘列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Limit|int|返回数据长度, 默认为20|No|
|Offset|int|数据偏移量, 默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|磁盘数量|**Yes**|
|DataSet|array|回收站磁盘列表|No|

## RecycleUDiskSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UDiskId|string|磁盘id|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|ExpiredTime|int|过期时间|**Yes**|
|CountdownTime|int|销毁倒计时|**Yes**|
|Name|string|磁盘名称|**Yes**|
|Size|int|磁盘容量|**Yes**|
|Tag|string|业务组|No|
|Zone|string|可用区|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeRecycleUDisk
&Region=cn-bj2
&Zone=cn-bj2-02
&Project=org-xxx
&Limit=20
&Offset=0
```

# Response Example
```
{
    "Action": "DescribeRecycleUDiskResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Tag": "Default", 
            "Name": "sniper", 
            "Zone": "cn-bj2-02", 
            "ExpiredTime": 1510309558, 
            "UDiskId": "bs-xxx", 
            "CountdownTime": 602781, 
            "CreateTime": 1508469548, 
            "Size": 20
        }
    ]
}
```

