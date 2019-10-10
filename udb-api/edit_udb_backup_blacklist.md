# 编辑备份黑名单-EditUDBBackupBlacklist

编辑UDB实例的备份黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DBId|string|DB实例Id,该值可以通过DescribeUDBInstance获取|**Yes**|
|Blacklist|string|黑名单，规范示例,指定库mysql.%;test.%; 指定表city.address;|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetBackupBlacklist
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
&Blacklist=mysql.%;test.%;city.address;
```

# Response Example
```
{
    "Action": "EditUDBBackupBlacklistResponse", 
    "RetCode": 0
}
```

