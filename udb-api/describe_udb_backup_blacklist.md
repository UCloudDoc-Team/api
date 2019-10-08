# 获取备份黑名单-DescribeUDBBackupBlacklist

获取UDB实例的备份黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id,该值可以通过DescribeUDBInstance获取|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Blacklist|string|DB的黑名单列表, db.%为指定库 dbname.tablename为指定表|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBBackupBlacklist
&Region=cn-bj2
&DBId=00f9868c-c7f5-4852-9eac-d200b678f0e1
```

# Response Example
```
{
    "Action": "DescribeUDBBackupBlacklistResponse", 
    "Blacklist": "abc.%;user.%;", 
    "RetCode": 0
}
```

