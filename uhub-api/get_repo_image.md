# 获取镜像仓库下的镜像-GetRepoImage

获取镜像仓库下的镜像

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|RepoName|string|镜像仓库名称|**Yes**|
|Offset|int|偏移量，默认0|No|
|Limit|int|显示数量，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int||**Yes**|
|ImageSet|array|镜像列表|**Yes**|

## ImageSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ImageName|string|镜像名称|**Yes**|
|PullCount|int|镜像被下载次数|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|UpdateTime|int|修改时间|**Yes**|
|LatestTag|string|最新push的Tag|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetRepoImage
&ProjectId=bbrEuvfC
&RepoName=idkTdEFo
&Offset=6
&Limit=6
&ProjectId=WsHgZAjU
```

# Response Example
```
{
    "Action": "GetRepoImageResponse", 
    "TotalCount": 5, 
    "RetCode": 0, 
    "ImageSet": [
        {
            "UpdateTime": 7, 
            "ImageName": "dCVBnkxg", 
            "PullCount": 4, 
            "CreateTime": 5, 
            "LatestTag": "iBvvYGkW"
        }, 
        {
            "UpdateTime": 2, 
            "ImageName": "HxZkUXvp", 
            "PullCount": 2, 
            "CreateTime": 2, 
            "LatestTag": "KNyBVrNA"
        }, 
        {
            "UpdateTime": 6, 
            "ImageName": "qCHiVQXX", 
            "PullCount": 6, 
            "CreateTime": 2, 
            "LatestTag": "dnvIjkJY"
        }, 
        {
            "UpdateTime": 8, 
            "ImageName": "lJszSnED", 
            "PullCount": 1, 
            "CreateTime": 9, 
            "LatestTag": "wGBJBifW"
        }, 
        {
            "UpdateTime": 1, 
            "ImageName": "BfChDnxj", 
            "PullCount": 9, 
            "CreateTime": 7, 
            "LatestTag": "CdySnxrY"
        }, 
        {
            "UpdateTime": 9, 
            "ImageName": "HUTQywVu", 
            "PullCount": 1, 
            "CreateTime": 9, 
            "LatestTag": "zqXMWiRd"
        }, 
        {
            "UpdateTime": 9, 
            "ImageName": "QfwwaABh", 
            "PullCount": 7, 
            "CreateTime": 8, 
            "LatestTag": "EymhuHfx"
        }, 
        {
            "UpdateTime": 2, 
            "ImageName": "ThYJXrVc", 
            "PullCount": 4, 
            "CreateTime": 5, 
            "LatestTag": "dnXrJOti"
        }, 
        {
            "UpdateTime": 3, 
            "ImageName": "qzCGPhQD", 
            "PullCount": 6, 
            "CreateTime": 2, 
            "LatestTag": "MCnyUuwU"
        }
    ]
}
```

