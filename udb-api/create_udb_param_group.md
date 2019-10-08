# 创建配置文件-CreateUDBParamGroup

从已有配置文件创建新配置文件

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|GroupName|string|新配置参数组名称|**Yes**|
|Description|string|参数组描述|**Yes**|
|SrcGroupId|int|源参数组id|**Yes**|
|DBTypeId|string|DB类型id，mysql/mongodb/postgesql按版本细分 1：mysql-5.1，2：mysql-5.5，3：percona-5.5，4：mysql-5.6，5：percona-5.6，6：mysql-5.7，7：percona-5.7，8：mariadb-10.0，9：mongodb-2.4，10：mongodb-2.6，11：mongodb-3.0，12：mongodb-3.2,13：postgresql-9.4，14：postgresql-9.6|**Yes**|
|RegionFlag|bool|是否是地域级别的配置文件，默认是false|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|int|新配置参数组id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUDBParamGroup     
&Region=cn-bj2
&Zone=cn-bj2-04
&DBTypeId=mysql-5.1
&SrcGroupId=2
&GroupName=mysql-xxx-config
&Description=xxx-config                   
```

# Response Example
```
{
    "Action": "CreateUDBParamGroupResponse", 
    "RetCode": 0, 
    "GroupId": 3
}
```

