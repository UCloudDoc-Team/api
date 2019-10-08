# 修改分布式数据库中间件名称-ChangeUDDBInstanceName

修改分布式数据库中间件名称

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|UDDBId|string|UDDB实例Id|**Yes**|
|NewName|string|名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ChangeUDDBInstanceName
&Region=cn-zj
&Zone=cn-zj-01
&UDDBId=UFwBjOqS
&NewName=NDyqLQdF
&ProjectId=XTQGkttB
```

# Response Example
```
{
    "Action": "ChangeUDDBInstanceNameResponse", 
    "RetCode": 0
}
```

