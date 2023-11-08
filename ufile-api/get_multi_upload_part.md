# **获取已上传成功的分片列表-ListParts**

## **简介**

获取未完成分片上传的对象的已上传成功的分片列表。

## **定义**

### **句法（Syntax）:**

```
GET /?muploadpart&uploadId=<uploadid>
Host: <bucket_name>.ufile.ucloud.cn
Authorization: <token>
```

### **请求参数（Request Parameters）**

| Parameter name | Type | Description | Required |
| --- | --- | --- | --- |
| uploadId | string | 上传ID。 | Yes |
| max-parts | Integer | 规定在US3响应中的最大Part数目。 | No |
| part-number-marker | Integer | 指定List的起始位置，只有Part Number数目大于该参数的Part会被列出。 | No |

### **响应（Responses）**

| Parameter name | Type | Description |
| --- | --- | --- |
| UploadId | string | 上传ID |
| Bucket | string | 空间名称 |
| Key | string | 文件名称 |
| Parts | array | 分片列表 |
| MaxParts | Integer | 返回请求中最大的Part数目。 |
| IsTruncated | Bool | 标明本次返回的ListParts结果列表是否被截断。 |
| Parts | Array | 分片信息。 |
| NextPartNumberMarker | Integer | 如果本次没有返回全部结果，响应请求中将包含NextPartNumberMarker元素，用于标明接下来请求的PartNumberMarker值。 |

### **分片信息（PartsItem）**

| Parameter name | Type | Description |
| --- | --- | --- |
| PartNum | Integer | 分片编号。 |
| Etag | string | 分片etag值。 |
| LastModified | Integer | Part上传的时间。 |
| Size | Integer | 已上传Part大小。 |

## **示例**

### **请求示例（Example Request）:**

```
GET /?muploadpart&uploadId=e5af977e-329c-4a25-b907-d8bc39ff95e3 HTTP/1.1
Host: example.cn-bj.ufileos.ucloud.cn
Authorization:UCloud pRAtiCbYdYI9wqHMqcQe0D9m16YpTsKBVL3GeBZ6wn6N+00uMrI7NQ==:VdDRXKoBjX6FnxjOz+HbLtswW50=
```

### **响应示例（Example Response）:**
```
{
    "UploadId": "e5af977e-329c-4a25-b907-d8bc39ff95e3",
    "Key": "large_file_version_4",
    "Bucket": "example",
    "Parts": [
        {
            "Etag": "K8y9LzjxXBPrfVqJ_Z2F9ZXiO8M=",
            "PartNum": 0,
            "LastModified": 1699432473,
            "Size": 33554432

        },
        {
            "Etag": "K8y9LzjxXBPrfVqJ_Z2F9ZXiO8M=",
            "PartNum": 1,
            "LastModified": 1699432473,
            "Size": 33554432
        },
        {
            "Etag": "8AELsK7_teqWNDghPCj9IdowvBA=",
            "PartNum": 2,
            "LastModified": 1699432473,
            "Size": 33554432
        }
    ]
}
```
