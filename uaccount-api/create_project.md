# 创建项目-CreateProject

创建项目

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectName|string|项目名称，不得与现有项目重名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ProjectId|string|所创建项目的Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateProject
&ProjectName=IhJYuYoB
```

# Response Example
```
{
    "Action": "CreateProjectResponse", 
    "ProjectId": "nWhecBSy", 
    "RetCode": 0
}
```

