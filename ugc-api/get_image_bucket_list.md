# 获取可用的镜像仓库列表-GetImageBucketList

获取可用的Docker镜像仓库列表，包括公有和私有的。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|BucketName|string|Docker镜像仓库名称，不填返回所有的镜像仓库|No|
|BucketType|string|All：用户所有可见的仓库， User：用户个人创建的仓库 ， Share：第三方公开镜像， 默认值：All|No|
|OrderBy|string|Default: 默认排序|No|
|Limit|int|返回数据长度，默认为20|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的镜像总数|No|
|ImageSet|array|镜像列表，详见 ImageBucketListSet|No|

## ImageBucketListSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BucketName|string|Docker镜像仓库名称|No|
|BucketType|string|Private：私有，Public：公有|No|
|ImageCount|int|仓库中含有的镜像个数|No|
|CreateTime|int|创建时间，格式为Unix时间戳|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetImageBucketList
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "GetImageBucketListResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "ImageSet": [
        {
            "BucketType": "Public", 
            "BucketName": "ucsdr.ucloud.cn:5000/ucs/helloworld:6", 
            "ImageCount": 10, 
            "CreateTime": 1234567890
        }
    ]
}
```

