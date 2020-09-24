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
|Authorization    |String|下载请求的授权签名，[UFile API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)  |No      |
|Range            |String|分片下载的文件范围                         |No      |
|If-Modified-Since|String|只返回从某时修改过的文件，否则返回304(not modified)|No      |

Request Elements

|Name             |Type  |Description                       |Required|
|---|---|---|---|
|ufileattname    |String|指定ufile返回请求的Content-Disposition头                   |No      |

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

> 注意: 成功下载时返回HTTP 200或206和数据体。

<table><tr><td bgcolor=orange>
 注意：示例中的Host为源站域名，如果您使用CDN下载，请将Host替换为CDN域名
  </td></tr></table>
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

