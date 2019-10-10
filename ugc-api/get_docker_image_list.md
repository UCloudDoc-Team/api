# 获取可用的镜像列表-GetDockerImageList

获取可用的Docker镜像列表，包括公有和私有的。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|BucketName|string|Docker镜像仓库名称|**Yes**|
|OrderBy|string|Default: 默认排序|No|
|Limit|int|返回数据长度，默认为20|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的镜像总数|No|
|ImageSet|array|Docker镜像列表，详见 DockerImageListSet|No|

## DockerImageListSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BucketName|string|Docker镜像名称|No|
|TagSet|array|Docker镜像版本列表，详见 DockerImageTagSet|No|
|UpdateTime|int|创建时间，格式为Unix时间戳|No|
|ResourceId|string|镜像的资源ID|No|
|OrgId|string|项目ID|No|

## DockerImageTagSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TagName|string|Docker镜像名称|No|
|CreateTime|int|创建时间，格式为Unix时间戳|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetDockerImageList
&Region=cn-bj2
&BucketName=ucs
```

# Response Example
```
{
    "Action": "GetDockerImageListResponse", 
    "TotalCount": 1, 
    "Message": "", 
    "RetCode": 0, 
    "ImageSet": [
        {
            "UpdateTime": 1234567890, 
            "ImageName": "ucsdr.ucloud.cn:5000/ucs/helloworld", 
            "TagSet": [
                {
                    "CreateTime": 1234567890, 
                    "TagName": "6"
                }
            ]
        }
    ]
}
```

