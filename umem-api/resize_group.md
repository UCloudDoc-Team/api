# 调整容量-ResizeURedisGroup

调整主备redis容量

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|string|组ID|**Yes**|
|Size|int|内存大小, 单位:GB (需要大于原size,且小于等于32) 目前仅支持1/2/4/8/16/32 G 六种容量规格|**Yes**|
|CouponId|int|代金券ID 请参考DescribeCoupon接口|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ResizeURedisGroup
&Region=cn-north-02
&GroupId=uredis-xxxx
&Size=16
&ProjectId=org-quk5zs
```

# Response Example
```
{
    "Action": "ResizeURedisGroupResponse", 
    "RetCode": 0
}
```

