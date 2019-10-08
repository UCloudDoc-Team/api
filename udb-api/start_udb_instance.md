# 启动云数据库-StartUDBInstance

启动UDB实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StartUDBInstance   
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "StartUDBInstanceResponse", 
    "RetCode": 0
}
```

