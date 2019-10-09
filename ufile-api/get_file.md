# 下载文件 - GetFile 

下载文件

Requests

Syntax:

```
GET /<file_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token> 
Range: bytes=byte_range
If-Modified-Since: <timestamp>
```
Request Parameters

Request Headers

|Name             |Type  |Description                       |Required|
|---|---|---|---|
|Authorization    |String|下载请求的授权签名                         |No      |
|Range            |String|分片下载的文件范围                         |No      |
|If-Modified-Since|String|只返回从某时修改过的文件，否则返回304(not modified)|No      |

Request Elements

说明: 未使用。

Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |请求下载文件的类型       |
|Content-Length|Integer|请求下载文件的长度       |
|Content-Range |String |请求下载文件的范围       |
|ETag          |String |请求下载文件在UFile的哈希值|
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误提示 |

> 注意: 成功下载时只返回HTTP 200回应和数据体。


<WRAP center round important 60%>
注意：示例中的Host为源站域名，如果您使用CDN下载，请将Host替换为CDN域名
</WRAP>


Example

Example Request:

```
GET /demofile HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
Example Response:

```
HTTP/1.1 200 OK
ETag: c5371fe3624d438cd8a59420a3221978
Content-Type: image/jpg
Content-Length: 1234

<data>
```
Example Response Only Get Partial Content:

```
HTTP/1.1 206 Partial Content
Content-Type: image/jpg
Content-Length: 34
Content-Range: bytes 0-10/34

<data>
```

