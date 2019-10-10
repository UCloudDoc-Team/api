# 创建镜像仓库-CreateDockerImageBucket

创建Docker镜像Bucket

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|BucketName|string|Docker镜像仓库名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateDockerImageBucket
&Region=cn-bj2
&BucketName=helloworld
```

# Response Example
```
{
    "Action": "CreateDockerImageBucketResponse", 
    "RetCode": 0
}
```

