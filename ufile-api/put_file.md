# 上传文件 - PutFile 

普通上传文件

Requests 

Request Method 

PUT

Syntax:

```
PUT /<key_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Length: <length>
Content-Type: <mimetype>
Content-MD5: <md5>
```
Request Parameters

Request Headers

| Name            | Type     |Description                                  |Required  |
|---|---|---|---|
| Authorization   | String   | 上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   | Yes       |
| Content-Length  | Integer  | 请求body部分即待上传文件的长度                            | Yes       |
| Content-Type    | String   | 请求body部分即待上传文件的类型                            | No        |
| Content-MD5     | String   | 文件内容的MD5摘要，为了保证数据的完整性，建议要配置Content-MD5检查一致性  | No        |
| X-Ufile-Storage-Class   | String   | 文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE                            | No        |

Request Elements

说明：未使用。

Responses

Response Headers

|Name          |Type   |Description      |
|---|---|---|
|Content-Type  |String |响应body部分的类型      |
|Content-Length|Integer|响应body部分的长度      |
|ETag          |String |已经上传文件在US3中的哈希值|
|X-SessionId   |String |请求失败时返回本次请求的会话Id |

Response Elements

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误消息 |

注意: 成功执行只会返回HTTP 200回应,不带body数据。

Example

Example Request:

```
PUT /demokey HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Length: 11434
Content-Type: image/jpg
Content-MD5: c5371fe3624d438cd8a59420a3221978

[11434 bytes of file data]
```
Example Response:

```
HTTP/1.1 200 OK
Content-Length: 0
ETag: AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH
```
Example Response with Error:

```
HTTP/1.1 404 Not Found
Content-Type: applicaton/json
Content-Length: 54 
X-SessionId: e2f4fc84-3936-4a2d-85b5-ef8f2e79933c

{
    "RetCode": -30010,
    "ErrMsg": "bucket not exist"
}
```
说明：在带错误的响应中还有一个响应头X-SessionId，可用于服务端进行具体的错误定位。



