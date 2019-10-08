# 获取已上传成功的分片列表-GetMultiUploadPart

获取已上传成功的分片列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UploadId|string|上传ID|**Yes**|

```
Syntax:
	GET /?muploadpart&uploadId=<uploadid>
	Host: <bucket_name>.ufile.ucloud.cn
	Authorization: <token> 

Request Headers
	Authorization 下载请求的授权签名
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ErrMsg|string|错误提示|No|
|UploadId|string|上传ID|No|
|Key|string|文件名称|No|
|Status|int|上传状态，0：未完成，1：完成|No|
|Parts|array|分片列表|No|

## PartsItem
|Parameter name|Type|Description|Required|
|---|---|---|---|
|PartNum|int|分片编号|No|
|Etag|string|分片etag值|No|

# Request Example
```
GET /?muploadpart&uploadId=e5af977e-329c-4a25-b907-d8bc39ff95e3 HTTP/1.1
Host: example.cn-bj.ufileos.ucloud.cn
Authorization:UCloud pRAtiCbYdYI9wqHMqcQe0D9m16YpTsKBVL3GeBZ6wn6N+00uMrI7NQ==:VdDRXKoBjX6FnxjOz+HbLtswW50=
```

# Response Example
```
{
    "Status": 0, 
    "RetCode": 0, 
    "Parts": [
        {
            "Etag": "K8y9LzjxXBPrfVqJ_Z2F9ZXiO8M=", 
            "PartNum": 0
        }, 
        {
            "Etag": "K8y9LzjxXBPrfVqJ_Z2F9ZXiO8M=", 
            "PartNum": 1
        }, 
        {
            "Etag": "8AELsK7_teqWNDghPCj9IdowvBA=", 
            "PartNum": 2
        }
    ], 
    "UploadId": "e5af977e-329c-4a25-b907-d8bc39ff95e3", 
    "Key": "large_file_version_4", 
    "ErrMsg": ""
}
```

