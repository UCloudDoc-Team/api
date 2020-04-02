# 新的误报接口-ModifyWafAttackFalseAlarmStatus

添加误报 取消误报操作都在这个接口

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SetStatus|string|枚举值，SetFalseAlarm:标记误报,UnsetFalseAlarm：取消误报|**Yes**|
|Key|string|记录的 ID值 作为Key传递|**Yes**|
|FullDomain|string|要操作的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafAttackFalseAlarmStatus
&SetStatus=SetFalseAlarm
&Key=oDagQhXL
&FullDomain=CNFhYjIz
&ProjectId=ESBlsTko
```

# Response Example
```
{
    "Action": "ModifyWafAttackFalseAlarmStatusResponse", 
    "RetCode": 0
}
```

