# 普通db升级为高可用-PromoteUDBInstanceToHA

普通db升级为高可用(只针对mysql5.5及以上版本)

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|IsLock|bool|升级时是否锁库，默认为锁库。不锁定：false；锁定：true。现在统一为不锁库，即false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=PromoteUDBInstanceToHA
&Region=cn-bj2
&DBId=udb-xxxxxx
```

# Response Example
```
{
    "Action": "PromoteUDBInstanceToHAResponse", 
    "RetCode": 0
}
```

