# 获取空间状态-GetUMemSpaceState

获取UMem内存空间列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SpaceId|string|内存空间ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|State|string|Starting:创建中 Running:运行中 Fail:失败|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetUMemSpaceState
&Region=cn-north-02
&Zone=cn-bj2-04
&SpaceId=umem-abcdes
```

# Response Example
```
{
    "Action": "GetUMemSpaceStateResponse", 
    "State": "Running", 
    "RetCode": 0
}
```

