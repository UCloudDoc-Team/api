# 卸载云硬盘-DetachUDisk

卸载某个已经挂载在指定UHost实例上的UDisk

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UHostId|string|UHost实例ID|**Yes**|
|UDiskId|string|需要卸载的UDisk实例ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UHostId|string|卸载的UHost实例ID|No|
|UDiskId|string|卸载的UDisk实例ID|No|

# Request Example
```
http://api.ucloud.cn/?Action=DetachUDisk
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xx
&UHostId=uhost-xxx
&UDiskId=bs-xxx
```

# Response Example
```
{
    "Action": "DetachUDiskResponse", 
    "UHostId": "uhost-xxx", 
    "RetCode": 0, 
    "UDiskId": "bs-xxx"
}
```

