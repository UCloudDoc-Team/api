# 从项目中移除成员-RemoveMemberFromProject

从项目中移除成员

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，请参考[GetProjectList接口](api/summary/get_project_list)的描述。不填写为默认项目，子帐号必须填写。 |**Yes**|
|MemberEmail|string|需要被移除成员Email|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=RemoveMemberFromProject
&ProjectId=lNAckBao
&MemberEmail=OejakjtT
```

# Response Example
```
{
    "Action": "RemoveMemberFromProjectResponse", 
    "RetCode": 0
}
```

