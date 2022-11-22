# 获取正在执行的分片上传id-GetMultiUploadId

## 简介

获取正在执行的分片上传id

## 定义

### 句法（Syntax）:

```
Syntax:
	GET /?muploadid&prefix=<prefix>&marker=<marker>&limit=<limit>
	Host: <bucket_name>.ufile.ucloud.cn
	Authorization: <token> 

Request Headers
	Authorization 下载请求的授权签名
```

### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Parameter name|Type|Description|Required|
|---|---|---|---|
|Prefix|string|前缀，utf-8编码，默认为空字符串|No|
|Marker|string|标志字符串，utf-8编码，默认为空字符串|No|
|Limit|int|id列表数目，默认为20|No|

**请求元素（Request Elements）**

|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ErrMsg|string|错误提示|No|
|NextMarker|string|下一个标志字符串，utf-8编码|No|
|DataSet|array|上传id列表|No|

**数据集（DataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UploadId|string|文件上传ID|No|
|FileName|string|文件名称|No|
|StartTime|int|上传开始时间，UNIX时间戳|No|

## 示例

### 请求示例（Example Request）:

```
GET /?muploadid&prefix=lar&marker=a&limit=20 HTTP/1.1
Host: example.cn-bj.ufileos.ucloud.cn
Authorization:UCloud pRAtiCbYdYI9wqHMqcQe0D9m16YpTsKBVL3GeBZ6wn6N+00uMrI7NQ==:VdDRXKoBjX6FnxjOz+HbLtswW50=
```

### 响应示例（Example Response）:
```
{
    "NextMarker": "", 
    "RetCode": 0, 
    "ErrMsg": "", 
    "DataSet": [
        {
            "UploadId": "3be8bd2b-4188-41d5-ac80-9ddf644a090c", 
            "StartTime": 1484116878, 
            "FileName": "large_file_version_2"
        }, 
        {
            "UploadId": "e5af977e-329c-4a25-b907-d8bc39ff95e3", 
            "StartTime": 1484117647, 
            "FileName": "large_file_version_4"
        }
    ]
}
```
## 备注

1. 该接口处于灰度状态，需要申请开通才能使用。
