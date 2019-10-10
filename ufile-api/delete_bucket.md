# 删除Bucket-DeleteBucket

删除Bucket

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|BucketName|string|待删除Bucket的名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BucketName|string|Bucket的名称|No|
|BucketId|string|Bucket的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteBucket
?BucketName=blue
```

# Response Example
```
{
    "Action": "DeleteBucketResponse", 
    "BucketId": "ufile-xxx", 
    "Retcode": 0, 
    "BucketName": "blue"
}
```

