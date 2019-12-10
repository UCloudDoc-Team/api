# 查询分布式redis备份-DescribeUMemBackup

查询分布式redis备份

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SpaceId|string|资源id|**Yes**|
|Offset|int|分页显示的起始偏移, 默认值为0|No|
|Limit|int|分页显示的条目数, 默认值为10|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|分布式redis 备份，数组的每个元素为每个分片的备份|No|

## UMemBackupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BackupName|string|备份名称|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|State|string|Starting:备份中 Done:完成|**Yes**|
|BackupId|string|空间的备份ID|**Yes**|
|BackupType|string|备份类型: auto(自动) ,manual(手动)|**Yes**|
|BlockCount|int|本次备份，分片的数量|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUMemBackup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=ttzQIEAS
&SpaceId=UgIbZdcJ
&Offset=3
&Limit=3
```

# Response Example
```
{
    "Action": "DescribeUMemBackupResponse", 
    "TotalCount": 9, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Protocol": "ADqlSMfS", 
            "BackupName": "wswsYgCj", 
            "SpaceId": "BockWwNG", 
            "BackupType": "XkJRGPby", 
            "State": "gvqEneLQ", 
            "BackupId": "YKTpXALa", 
            "CreateTime": 3
        }
    ]
}
```

