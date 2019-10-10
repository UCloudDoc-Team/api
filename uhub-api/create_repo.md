# 创建镜像仓库-CreateRepo

创建镜像仓库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RepoName|string|仓库名称，不可修改|**Yes**|
|IsShared|bool|镜像仓库是否公开，公开为true、不公开为false;默认为false|No|
|Description|string|仓库备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|有错误时返回内容|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateRepo
&ProjectId=MKKmXuQq
&RepoName=cClamyhb
&IsShared=false
&Description=BEUmUVDI
&ProjectId=MiejULgA
```

# Response Example
```
{
    "Action": "CreateRepoResponse", 
    "Message": "DcRJngSm", 
    "RetCode": 0
}
```

