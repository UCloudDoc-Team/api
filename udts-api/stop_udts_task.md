# 停止UDTS任务-StopUDTSTask

停止UDTS任务

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|TaskId|string|任务 ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=StopUDTSTask
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=glcXFbjq
&TaskId=oUfNLhbg
```

# Response Example
```
{
    "Action": "StopUDTSTaskResponse", 
    "Message": "FnHTUqMZ", 
    "RetCode": 0
}
```

