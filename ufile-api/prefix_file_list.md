# 前缀列表查询 - PrefixFileList 

获取Bucket中指定文件前缀的文件列表

Requests

Syntax:

```
GET /?list&prefix=<prefix>&marker=<marker>&limit=<limit>
Host: <bucket_name>.ufile.ucloud.cn
Authorization: <token> 
```
Request Parameters

Request Headers

|Name             |Type  |Description                       |Required|
|---|---|---|---|
|prefix           |String|前缀，utf-8编码，默认为空字符串                         |No      |
|marker|String|标志字符串，utf-8编码，默认为空字符串)                         |No      |
|limit|Integer|文件列表数目，默认为20                         |No      |
|Authorization    |String|下载请求的授权签名，[UFile API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)         |No      |

Request Elements

说明: 未使用。

Responses

Response Elements

|Name          |Type   |Description     |
|---|---|---|
|BucketName  |String |Bucket的名称       |
|BucketId   |String |Bucket的ID       |
|NextMarker  |String |下一个标志字符串，utf-8编码      |
|DataSet    |Array  |文件列表   |

DataSet Item

|Name   |Type   |Description|
|---|---|---|
|BucketName  |String |文件所属Bucket名称      |
|FileName   |String |文件名称,utf-8编码      |
|Hash      |String |文件hash值     |
|MimeType   |Array  |文件mimetype  |
|Size	|Integer	|文件大小 |
|CreateTime |Integer |文件创建时间 |
|ModifyTime |Integer	|文件修改时间 |
| StorageClass |String		|文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE |

Example

Example Request:

```
GET /?list&prefix=aaa
Host: blue.ufile.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
Example Response:

```
{
    "BucketName": "blue",
    "BucketId": "ufile-qs20fr",
    "NextMarker": "",
    "DataSet": [
        {
            "BucketName": "blue",
            "FileName": "aaa.jpg",
            "Hash": "fbfc1aba39fdac0e0f298461970529d3",
            "MimeType": "image/jpeg",
            "Size": 344500,
            "CreateTime": 1408298579,
            "ModifyTime": 1408298579
       }
    ]
}
```
