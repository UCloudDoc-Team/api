# 表单上传 - PostFile 

表单上传文件

说明：适合使用浏览器的场景并且上传文件内容可以在一次HTTP请求完成，并且所有PUT上传支持的参数都可以在表单上传中指定。

Requests

Syntax:

```
POST / HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Content-Type: multipart/form-data; boundary=----UCloudPOSTFormTestBoundary
Content-Length: <length>

<file_content>
```
Request Headers

| Name            | Type     | Description                                 |Required  |
|---|---|---|---|
| Content-Type    | String   | 待上传文件的类型,必须为multipart/form-data               | Yes       |
| Content-Length  | Integer  | 请求body的长度                                     | Yes       |
| Content-MD5     | String   | 文件内容的MD5摘要，为了保证数据的完整性，建议要配置Content-MD5并检查一致性  | No        |
| X-Ufile-Storage-Class   | String   | 文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE                            | No        |

Request Parameters

|Name         |Type  |Description    |Required|
|---|---|---|---|
|FileName     |String|Bucket中文件的名称   |Yes     |
|Authorization|String|上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)       |Yes     |
|Content-Type |String|上传文件本身的MimeType|No      |

<HTML><blockquote>
   **注意:**     - 以上参数是在form表单中的参数。
    - POST 表单上传时签名使用的是 form 表单参数的 Content-Type(即上传文件本身的 mimetype), 而非本次 HTTP 请求的 Content-Type。
</blockquote></HTML>
Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的大小     |
|ETag          |String |完成上传的文件的哈希值     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误消息 |

> 注意: 成功执行只会返回HTTP 200回应,不带body数据.

Example

Example Request:

```
POST / HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Content-MD5: c5371fe3624d438cd8a59420a3221978
Content-Type: multipart/form-data; boundary=----UCloudPOSTFormBoundary

------UCloudPOSTFormBoundary
Content-Disposition: form-data; name="FileName"

demofile
------UCloudPOSTFormBoundary
Content-Disposition: form-data; name="Authorization"

UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
------UCloudPOSTFormBoundary
Content-Disposition: form-data; name="file"; filename="MyFilename.jpg"
Content-Type: image/jpeg

<file_content>
------UCloudPOSTFormBoundary--
```
Example Response:

```
HTTP/1.1 200 OK
Content-Length: 0
ETag: AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH
```


