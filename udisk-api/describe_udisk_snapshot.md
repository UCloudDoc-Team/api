# 获取快照列表-DescribeUDiskSnapshot

获取UDisk快照

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|返回数据长度, 默认为20|No|
|UDiskId|string|UDiskId,返回该盘所做快照.(必须同时传Zone)|No|
|SnapshotId|string|快照id，SnapshotId , UDiskId 同时传SnapshotId优先|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|JSON 格式的Snapshot列表, 详细参见 UDiskSnapshotSet|No|
|TotalCount|int|根据过滤条件得到的总数|No|

## UDiskSnapshotSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SnapshotId|string|快照Id|**Yes**|
|Name|string|快照名称|**Yes**|
|UDiskId|string|快照的源UDisk的Id|**Yes**|
|UDiskName|string|快照的源UDisk的Name|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|Size|int|容量单位GB|**Yes**|
|Status|string|快照状态，Normal:正常,Failed:失败,Creating:制作中|**Yes**|
|DiskType|int|磁盘类型，0:数据盘，1:系统盘|**Yes**|
|ExpiredTime|int|过期时间|No|
|Comment|string|快照描述|No|
|IsUDiskAvailable|bool|对应磁盘是否处于可用状态|No|
|Version|string|快照版本|No|
|UHostId|string|对应磁盘制作快照时所挂载的主机|No|
|UKmsMode|string|是否是加密盘快照，是:"Yes", 否:"No"|No|
|CmkId|string|该快照的cmk id|No|
|DataKey|string|该快照的密文密钥|No|
|CmkIdStatus|string|该快照cmk的状态, Enabled(正常)，Disabled(失效)，Deleted(删除)，NoCmkId(非加密盘)|No|
|CmkIdAlias|string|cmk id 别名|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDiskSnapshot
&Region=cn-bj2
&SnapshotId=bsSnap-xxx
```

# Response Example
```
{
    "Action": "DescribeUDiskSnapshotResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Comment": "test", 
            "ChargeType": "Year", 
            "UHostId": "uhost-xxx", 
            "Version": "1.0", 
            "Name": "test", 
            "UDiskName": "apidoctest", 
            "DiskType": 0, 
            "Status": "Normal", 
            "ExpiredTime": 1402039500, 
            "UDiskId": "bs-xxx", 
            "SnapshotId": "bsSnap-xxx", 
            "IsUDiskAvailable": true, 
            "CreateTime": 1402039500, 
            "Size": "100"
        }
    ]
}
```

