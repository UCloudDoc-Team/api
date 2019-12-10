# 创建分布式redis备份-CreateUMemBackup

创建分布式redis备份

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SpaceId|string|资源id|**Yes**|
|BackupName|string|请求创建备份的名称 (范围[6-63],只能包含英文、数字以及符号-和_)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BackupId|string|备份Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUMemBackup
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=LxXTAasF
&SpaceId=GDuOtnyg
&BackupName=mXToeXpx
&BlockId=SCvCWRWH
```

# Response Example
```
{
    "Action": "CreateUMemBackupResponse", 
    "BackupId": "uBllGFJq", 
    "RetCode": 0
}
```

