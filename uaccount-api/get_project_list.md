# 获取帐号下的项目列表-GetProjectList

获取项目列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IsFinance|string|是否是财务账号（Yes：是，No：否）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ProjectCount|int|项目总数|**Yes**|
|ProjectSet|array|JSON格式的项目列表实例|**Yes**|

## ProjectListInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID|**Yes**|
|ProjectName|string|项目名称|**Yes**|
|CreateTime|int|创建时间(Unix时间戳)|**Yes**|
|IsDefault|bool|是否为默认项目|**Yes**|
|ResourceCount|int|项目下资源数量（已废弃，不建议使用）|**Yes**|
|MemberCount|int|项目下成员数量|**Yes**|
|ParentId|string|父项目ID（已废弃）|No|
|ParentName|string|父项目名称（已废弃）|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetProjectList
```

# Response Example
```
{
    "Action": "GetProjectListResponse", 
    "ProjectCount": 2, 
    "ProjectSet": [
        {
            "ResourceCount": 52, 
            "MemberCount": 1, 
            "ProjectId": "org-1", 
            "ProjectName": "ucloud", 
            "CreateTime": 1342434682, 
            "IsDefault": true
        }, 
        {
            "ResourceCount": 10, 
            "MemberCount": 0, 
            "ProjectId": "org-2", 
            "ProjectName": "test", 
            "CreateTime": 1468225814, 
            "IsDefault": false
        }
    ], 
    "RetCode": 0
}
```

