# 初始化分片 - InitiateMultipartUpload 

初始化分片上传

Requests

Syntax:

```
POST /<object_name>?uploads HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Length: 0
```
Request Parameters

Request Headers

|Name          |Type   |Description|Required|
|---|---|---|---|
|Authorization |String |上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |Yes     |
|Content-Length|Integer|请求body部分的长度|No      |
| X-Ufile-Storage-Class   | String   | 文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE                            | No        |
| X-Ufile-Meta- *   | String   | US3中规定所有以X-Ufile-Meta-为前缀的参数视为用户自定义元数据（User Meta），比如x-ufile-meta-location。一个文件可以有多个类似的参数，但所有的User Meta总大小不能超过8KB。这些User Meta信息会在GetFile或者HeadFile的时候在HTTP头部中返回。   | No        |

Request Elements

说明：未使用。

Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name    |Type   |Description       |
|---|---|---|
|UploadId|String |本次分片上传的上传Id       |
|BlkSize |Integer|分片的块大小            |
|Bucket  |String |上传文件所属Bucket的名称   |
|Key     |String |上传文件在Bucket中的Key名称|

Example

Example Request:

```
POST /demokey?uploads HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Length: 0
```
Example Response:

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 121

{
    "UploadId": "0f188eb2-5e19-49c3-94c9-36fb5a0ff72a",
    "BlkSize": 4194304,
    "Bucket": "demobucket",
    "Key": "demokey"
}
```
