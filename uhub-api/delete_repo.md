# 删除镜像仓库-DeleteRepo

删除镜像仓库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RepoName|string|镜像仓库名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteRepo
&ProjectId=bkMJlJgA
&RepoName=knXPUThp
&ProjectId=gxLJpsoY
```

# Response Example
```
{
    "Action": "DeleteRepoResponse", 
    "RetCode": 0
}
```

