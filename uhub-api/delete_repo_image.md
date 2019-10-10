# 删除镜像-DeleteRepoImage

删除镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RepoName|string|镜像仓库名称|**Yes**|
|ImageName|string|镜像名称|**Yes**|
|TagName|string|不指定tag则删除全部tag|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteRepoImage
&ProjectId=CSGiTSjx
&RepoName=QxQePyTQ
&ImageName=bqWkUZbf
&TagName=ttebrRqp
```

# Response Example
```
{
    "Action": "DeleteRepoImageResponse", 
    "RetCode": 0
}
```

