# 调整容量-ResizeUMemSpace

调整内存空间容量

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SpaceId|string|UMem 内存空间Id|**Yes**|
|Size|int|内存大小, 单位:GB (需要大于原size,<= 1024)|**Yes**|
|CouponId|string|使用的代金券Id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeUMemSpace
&Region=cn-north-02
&Zone=cn-bj2-04
&SpaceId=umem-xxxx
&Size=20
```

# Response Example
```
{
    "Action": "ResizeUMemSpaceResponse", 
    "RetCode": 0
}
```

