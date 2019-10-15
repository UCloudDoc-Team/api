# 修改DB实例的管理员密码-ModifyUDBInstancePassword

修改DB实例的管理员密码

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|实例的ID,该值可以通过DescribeUDBInstance获取|**Yes**|
|Password|string|实例的新密码|**Yes**|
|AccountName|string|sqlserver帐号，仅在sqlserver的情况下填该参数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyUDBInstancePassword
&Region=cn-bj2
&DBId=udb-xxxxxx
&ProjectId=7
&Password=adjk
```

# Response Example
```
{
    "Action": "ModifyUDBInstancePasswordResponse", 
    "RetCode": 0
}
```

