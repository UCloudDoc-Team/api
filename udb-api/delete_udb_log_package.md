# 删除UDB日志包-DeleteUDBLogPackage

删除UDB日志包

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BackupId|int|日志包id，可通过DescribeUDBLogPackage获得|**Yes**|
|BackupZone|string|跨可用区高可用备库所在可用区|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUDBLogPackage
&Region=cn-bj2
&Zone=cn-bj2-04
&BackupId=5160
```

# Response Example
```
{
    "Action": "DeleteUDBLogPackageResponse", 
    "RetCode": 0
}
```

