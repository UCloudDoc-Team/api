# 重命名云硬盘-RenameUDisk

重命名UDisk

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UDiskId|string|重命名的UDisk的Id|**Yes**|
|UDiskName|string|重命名UDisk的name|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RenameUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xx
&UDiskId=2AFCD36A-2A47-4D26-8514-CAA3FC2DC6BF
&UDiskName=udisk_2
```

# Response Example
```
{
    "Action": "RenameUDiskResponse", 
    "RetCode": 0
}
```

