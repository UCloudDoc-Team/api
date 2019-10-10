# 更新镜像仓库-UpdateRepo

更新镜像仓库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|RepoName|string|镜像仓库名称，不可修改|**Yes**|
|IsShared|string|false设置为私有；true设置为公有。默认false|No|
|Description|string|备注|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|错误的时候返回|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateRepo
&ProjectId=mWpHCsFn
&RepoName=jkbIyZQz
&IsShared=LaamHCfd
&Description=DTXnLsNO
&ProjectId=BpuNmLPb
```

# Response Example
```
{
    "Action": "UpdateRepoResponse", 
    "Message": "XliiipxF", 
    "RetCode": 0
}
```

