# 获取目录文件列表-ListObjects

用于以目录形式列出Bucket下的文件信息  （**注意**：目前该接口只有**北京、上海、广州、台北、首尔**地域支持）

# Request
## Syntax:
```
GET /?listobjects&prefix=<prefix>&marker=<marker>&max-keys=<max-keys>&delimiter=<delimiter> HTTP/1.1
Host: <bucket_name>.ufile.ucloud.cn
Authorization: <token>
```

# Request Parameters
## Request Header
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Authorization|string|上传请求的授权签名，[UFile API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95) 	|**Yes**|

## Request Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Prefix|string|返回以Prefix作为前缀的目录文件列表|No|
|Marker|string|返回以字母排序后，大于Marker的目录文件列表|No|
|MaxKeys|int|指定返回目录文件列表的最大数量，默认值为100，不超过1000|No|
|Delimiter|string|目录分隔符，当前只支持"/"和" "，当Delimiter设置为"/"时，返回目录形式的文件列表，当Delimiter设置为" "时，返回非目录层级文件列表|No|

# Response
## Response Header
|Parameter name|Type|Description|
|---|---|---|
|Content-Length|Integer|响应body部分的长度|
|Content-Type|String|响应body部分的类型|

## Response Elements
|Parameter name|Type|Description|
|---|---|---|
|Name|string|Bucket名称|
|Prefix|string|查询结果的前缀|
|MaxKeys|int|查询结果的最大数量|
|Delimiter|string|查询结果的目录分隔符|
|IsTruncated|bool|返回结果是否被截断。若值为true，则表示仅返回列表的一部分，NextMarker可作为之后迭代的游标|
|NextMarker|string|可作为查询请求中的的Marker参数，实现迭代查询|
|Contents|array|文件列表|
|CommonPrefixes|array|以Delimiter结尾，并且有共同前缀的目录列表|

## Contents
|Parameter name|Type|Description|
|---|---|---|
|Key|string|文件名称|
|MimeType|string|文件mimetype|
|ETag|string|标识文件内容|
|Size|string|文件大小|
|StorageClass|string|文件存储类型|
|LastModified|int|文件最后修改时间|
|CreateTime|int|文件创建时间|

## CommonPrefixes
|Parameter name|Type|Description|
|---|---|---|
|Prefix|string|以Delimiter结尾的公共前缀目录名|

# Request Example
```
GET /?listobjects&delimiter=/&max-keys=2 HTTP/1.1
Host: buc-test.ufile.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```

# Response Example
```
HTTP/1.1 200 OK
Content-Length: 347
Content-Type: application/json
{
    "Name":"buc-test",
    "Prefix":"",
    "MaxKeys":"2",
    "Delimiter":"/",
    "IsTruncated":true,
    "NextMarker":"0221.txt",
    "Contents":[
      {
        "Key":"0221.txt",
        "MimeType":"text/x-c",
        "ETag":"AQAAAMwtcq6V6wgHkQIHOrPu7H6YWuSo",
        "Size":"6",
        "StorageClass":"STANDARD",
        "LastModified":1552039614,
        "CreateTime":1552039614
     }
    ],
    "CommonPrefixes":[
     {
         "Prefix":"/"
     }
    ]
}
```

