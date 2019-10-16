# 挂载云硬盘-AttachUDisk

将一个可用的UDisk挂载到某台主机上，当UDisk挂载成功后，还需要在主机内部进行文件系统操作

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|UHostId|string|UHost实例ID|**Yes**|
|UDiskId|string|需要挂载的UDisk实例ID.|**Yes**|
|MultiAttach|string|是否允许多点挂载（Yes: 允许多点挂载， No: 不允许多点挂载， 不填默认Yes ）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostId|string|挂载的UHost实例ID|No|
|UDiskId|string|挂载的UDisk实例ID|No|

# Request Example
```
http://api.ucloud.cn/?Action=AttachUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&UHostId=uhost-xxx
&UDiskId=bs-xxx
&MultiAttach=Yes
```

# Response Example
```
{
    "Action": "AttachUDiskResponse", 
    "UHostId": "uhost-xxx", 
    "RetCode": 0, 
    "UDiskId": "bs-xxx"
}
```

