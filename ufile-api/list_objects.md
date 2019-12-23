# 获取目录文件列表-ListObjects

用于以目录形式列出Bucket下的文件信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Authorization|string|获取目录文件列表请求的授权签名|**Yes**|
|Prefix|string|返回以Prefix作为前缀的目录文件列表|No|
|Marker|string|返回以字母排序后，大于Marker的目录文件列表|No|
|MaxKeys|int|指定返回目录文件列表的最大数量，默认值为100，不超过1000|No|
|Delimiter|string|目录分隔符，默认为'/'，当前只支持是'/'|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Name|string|Bucket名称|No|
|Prefix|string|查询结果的前缀|No|
|MaxKeys|int|查询结果的最大数量|No|
|Delimiter|string|查询结果的目录分隔符|No|
|IsTruncated|bool|返回结果是否被截断。若值为true，则表示仅返回列表的一部分，NextMarker可作为之后迭代的游标|No|
|NextMarker|string|可作为查询请求中的的Marker参数，实现迭代查询|No|
|Contents|array|文件列表|No|
|CommonPrefixes|array|以Delimiter结尾，并且有共同前缀的目录列表|No|

## Contents
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Key|string|文件名称|**Yes**|
|MimeType|string|文件mimetype|**Yes**|
|ETag|string|标识文件内容|**Yes**|
|Size|string|文件大小|**Yes**|
|StorageClass|string|文件存储类型|**Yes**|
|LastModified|int|文件最后修改时间|**Yes**|
|CreateTime|int|文件创建时间|**Yes**|

## CommonPrefixes
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Prefix|string|以Delimiter结尾的公共前缀目录名|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ListObjects
&Authorization=otXXMMnW
&Prefix=igviJcXo
&Marker=kkGeLMFB
&MaxKeys=9
&Delimiter=nTdYKjnA
```

# Response Example
```
{
    "Name": "pPznOxlP", 
    "NextMarker": "vZpbukOU", 
    "Delimiter": "JMCjvzKE", 
    "MaxKeys": 6, 
    "Prefix": "NlRgDPOX", 
    "Action": "ListObjectsResponse", 
    "CommonPrefixes": [
        {
            "Prefix": "cfnzRqeg"
        }
    ], 
    "IsTruncated": false, 
    "Contents": [
        {
            "MimeType": "OjCSLEPm", 
            "LastModified": 4, 
            "ETag": "hEfUAHLV", 
            "StorageClass": "yOVtxMEh", 
            "Key": "GmwMhdPm", 
            "CreateTime": 2, 
            "Size": "QXERFtCZ"
        }
    ], 
    "RetCode": 0
}
```

