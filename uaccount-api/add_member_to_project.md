# 添加成员到项目-AddMemberToProject

添加成员到项目

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，请参考[GetProjectList接口](../summary/get_project_list.html)的描述。不填写为创建时间最早的项目。 |No|
|MemberEmail|string|被加入成员Email|**Yes**|
|CharacterId|string|被加入成员归属角色ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=AddMemberToProject
&ProjectId=eiuBIVTf
&MemberEmail=test@exmaple.com
&CharacterId=test
```

# Response Example
```
{
    "Action": "AddMemberToProjectResponse", 
    "RetCode": 0
}
```

