# **获取正在执行的分片上传id-GetMultiUploadId**

## **简介**

获取正在执行的分片上传id。

## **定义**

### **句法（Syntax）:**

```
  GET /?muploadid&prefix=<prefix>&marker=<marker>&limit=<limit>
  Host: <bucket_name>.ufile.ucloud.cn
  Authorization: <token>
```

### **请求参数（Request Parameters）**

**请求头（Request Headers）**

| Parameter name | Type | Description | Required |
| --- | --- | --- | --- |
| prefix | string | 前缀，utf-8编码，默认为空字符串 | No |
| marker | string | 标志字符串，utf-8编码，默认为空字符串 | No |
| limit | int | id列表数目，默认为20 | No |
| upload-id-marker | string | 与key-marker参数配合使用，用于指定返回结果的起始位置。 | No |

**响应元素（Reponse Elements）**

| Parameter name | Type | Description |
| --- | --- | --- |
| NextMarker | string | 下一个标志字符串，utf-8编码 |
| DataSet | array | 上传id列表。 |
| Bucket | string | 空间名字。 |
| UploadIdMarker |  | 如果本次没有返回全部结果，响应请求中将包含NextUploadMarker元素，用于表示接下来请求的UploadMarker值。 |
| IsTruncated | Bool | 表示本次返回的MultipartUpload结果列表是否被截断。 |
数据集（DataSet）

| Parameter name | Type | Description |
| --- | --- | --- |
| UploadId | string | 文件上传ID |
| FileName | string | 文件名称 |
| StartTime | int | 上传开始时间，UNIX时间戳 |
| StorageClass | string | 存储类型 |

## **示例**

### **请求示例（Example Request）:**

```
GET /?muploadid&prefix=lar&marker=a&limit=20 HTTP/1.1
Host: example.cn-bj.ufileos.ucloud.cn
Authorization:UCloud pRAtiCbYdYI9wqHMqcQe0D9m16YpTsKBVL3GeBZ6wn6N+00uMrI7NQ==:VdDRXKoBjX6FnxjOz+HbLtswW50=
```

### **响应示例（Example Response）:**
```
{
    "NextMarker": "",
    "RetCode": 0,
    "ErrMsg": "",
    "DataSet": [
        {
            "UploadId": "3be8bd2b-4188-41d5-ac80-9ddf644a090c",
            "StartTime": 1484116878,
            "FileName": "large_file_version_2",
            "StorageClass": "STANDARD"
        },
        {
            "UploadId": "e5af977e-329c-4a25-b907-d8bc39ff95e3",
            "StartTime": 1484117647,
            "FileName": "large_file_version_4",
            "StorageClass": "STANDARD"
        }
    ]
}
```