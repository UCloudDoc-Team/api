# 获取文件列表-GetFileList

获取Bucket的文件列表

```
注：该API已废弃，请以[[./prefix_file_list]]代替
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|BucketName|string|Bucket名称|**Yes**|
|Offset|string|获取Bucket中文件列表的偏移数目，默认为0|No|
|Limit|string|获取Bucket中文件列表的限制数目，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|BucketName|string|Bucket的名称|No|
|BucketId|string|Bucket的ID|No|
|DataSet|array|Bucket下的文件列表 参数见 UFileListSet|No|

## UFileListSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|BucketName|string|文件所属Bucket的名称|No|
|FileName|string|Bucket中文件的名称|No|
|Hash|string|文件的哈希值，默认为md5|No|
|MimeType|string|文件的MIME类型|No|
|Size|int|文件大小|No|
|CreateTime|int|文件创建时间|No|
|ModifyTime|int|文件修改时间|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetFileList
&BucketName=blue
```

# Response Example
```
{
    "Action": "GetFileListResponse", 
    "BucketId": "ufile-qs20fr", 
    "DataSet": [
        {
            "MimeType": "image/jpeg", 
            "Hash": "fbfc1aba39fdac0e0f298461970529d3", 
            "FileName": "\u58c1\u7eb8.jpg", 
            "BucketName": "blue", 
            "ModifyTime": 1408298579, 
            "CreateTime": 1408298579, 
            "Size": 344500
        }
    ], 
    "Retcode": 0, 
    "BucketName": "blue"
}
```

