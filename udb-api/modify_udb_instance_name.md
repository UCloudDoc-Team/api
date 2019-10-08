# 修改云数据库名称-ModifyUDBInstanceName

重命名UDB实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|实例的Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|Name|string|实例的新名字, 长度要求为6~63位|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUDBInstanceName     
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&Name=xxx-yyy                          
```

# Response Example
```
{
    "Action": "ModifyUDBInstanceNameResponse", 
    "RetCode": 0
}
```

