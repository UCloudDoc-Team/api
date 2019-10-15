# 获取镜像仓库-GetRepo

获取镜像仓库

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Type|string|private私有仓库，public公共仓库，默认public|No|
|Offset|int|偏移量，默认0|No|
|Limit|int|数量，默认20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总的仓库数量|**Yes**|
|RepoSet|array|镜像仓库列表|**Yes**|

## RepoSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RepoName|string|镜像仓库名称|**Yes**|
|CreateTime|int|仓库创建时间|**Yes**|
|UpdateTime|int|仓库更新时间|**Yes**|
|Description|string|镜像仓库描述|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetRepo
&ProjectId=DPQzQxpe
&Type=EzVxntiX
&Offset=1
&Limit=3
```

# Response Example
```
{
    "Action": "GetRepoResponse", 
    "TotalCount": 2, 
    "RepoSet": [
        "ntmEsbYx", 
        "ORXeSVYD", 
        "NLnhyWGk", 
        "RjXuIDDg", 
        "qrDktRNL", 
        "aVhDFvep", 
        "JvxMmIMA", 
        "BlemVnAI", 
        "uekjGZaL"
    ], 
    "RetCode": 0
}
```

