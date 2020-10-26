# 上传分片 - UploadPart 

上传文件分片

> 在初始化一个Multipart Upload之后，可以根据指定的key_name和upload_id来上传一个文件的分片。每一个文件分片都有一个号码part_number，该号码标识了这块分片数据在整个文件内的相对位置。

Requests

Syntax:

```
PUT /<key_name>?uploadId=<upload_id>&partNumber=<part_number> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Type: <mimetype>
Content-Length: <length>
```
Request Parameters

Request Headers

|Name          |Type   |Description      |Required|
|---|---|---|---|
|Authorization |String |上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)  |Yes     |
|Content-Length|Integer|请求body部分即待上传分片的长度|Yes     |
|Content-Type  |String |上传请求body部分的类型    |Yes     |

注意：上传分片请求的Content-Length必须等于初始化上传返回的分片块大小，否则完成上传时校验会失败。各个分片可以 独立并发上传。

Request Elements

说明：未使用。

Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|ETag          |String |已上传分片的哈希值       |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name      |Type   |Description|
|---|---|---|
|PartNumber|Integer|本次分片上传的分片号码|

Example

Example Request:

```
PUT /demokey?uploadId=0f188eb2-5e19-49c3-94c9-36fb5a0ff72a&partNumber=0 HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Type: application/octet-stream
Content-Length: 4194304

[4194304 bytes of data, as part of a file]
```
Example Response:

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 21
ETag: AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH
Content-Type: application/json
Content-Length: 21

{
   "PartNumber": 0
}
```
