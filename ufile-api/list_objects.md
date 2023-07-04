# 获取目录文件列表-ListObjects

## 简介

用于以目录形式列出Bucket下的文件信息

## 定义

### 句法（Syntax）:

```
GET /?listobjects&prefix=<prefix>&marker=<marker>&max-keys=<max-keys>&delimiter=<delimiter> HTTP/1.1
Host: <bucket_name>.ufile.ucloud.cn
Authorization: <token>
```

### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Parameter name|Type|Description|Required|
|---|---|---|---|
|Authorization|string|上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95) 	|**Yes**|

**请求元素（Request Elements）**

|Parameter name|Type|Description|Required|
|---|---|---|---|
|Prefix|string|返回以Prefix作为前缀的目录文件<br>当delimiter为("")时，返回的列表包含prefix内的所有子文件及子文件夹<br>当delimiter为("/")时，返回prefix下的所有文件和子文件夹,但不显示子文件夹下递归的目录和文件。<br>ps：当delimiter为("/")时，且prefix以("/")结尾时，列表返回不会包含与prefix相同的文件/目录名的对象|No|
|Marker|string|返回以字母排序后，大于Marker的目录文件列表<br>默认值:无|No|
|Limit|int|指定返回目录文件列表的最大数量<br>范围:[0,1000]<br>默认值:100|No|
|Delimiter|string|目录分隔符，当前只支持"/"和"".<br>当Delimiter设置为"/"时，返回目录形式的文件列表.<br>当Delimiter设置为""时，返回非目录层级文件列表|No|

### 响应（Responses）

**响应头（Response Headers）**

|Parameter name|Type|Description|
|---|---|---|
|Content-Length|Integer|响应body部分的长度|
|Content-Type|String|响应body部分的类型|

**响应元素（Response Elements）**

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

**内容（Contents）**

|Parameter name|Type|Description|
|---|---|---|
|Key|string|文件名称|
|MimeType|string|文件mimetype|
|ETag|string|标识文件内容|
|Size|string|文件大小|
|StorageClass|string|文件存储类型|
|LastModified|int|文件最后修改时间|
|CreateTime|int|文件创建时间|
|UserMeta|键值对|用户元数据|

**通用前缀（CommonPrefixes）**

|Parameter name|Type|Description|
|---|---|---|
|Prefix|string|以Delimiter结尾的公共前缀目录名|

## 示例

### 请求示例（Example Request）:
```
GET /?listobjects&delimiter=/&max-keys=2 HTTP/1.1
Host: buc-test.ufile.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```

### 响应示例（Example Response）:
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

