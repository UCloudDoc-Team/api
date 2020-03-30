# 启动UDTS服务-StartUDTSTask

启动UDTS服务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TaskId|string|任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StartUDTSTask
&ProjectId=org-asgd12
&TaskId=udts-avew24
```

# Response Example
```
{
    "Action": "StartUDTSTaskResponse", 
    "Message": "", 
    "RetCode": 0
}
```

