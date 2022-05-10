## 文件拷贝 - Copy

调用Copy接口拷贝同一地域下相同或不同存储空间（Bucket）之间的文件（Object）。

Requests

Syntax:

```
PUT /<key_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Length: <length>
X-Ufile-Copy-Source: </SourceBucketName/SourceObjectName>
```

Request Parameters

Request Headers

| Name                       | Type    | Description                                                  | Required |
| -------------------------- | ------- | ------------------------------------------------------------ | -------- |
| Authorization              | String  | 上传请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=文件管理签名算法) | Yes      |
| Content-Length             | Integer | 请求body部分即待上传文件的长度                               | Yes      |
| X-Ufile-Copy-Source        | String  | 指定拷贝的源地址                                             | Yes      |
| X-Ufile-Metadata-Directive | String  | 指定如何设置目标Object的元信息。<br> *  COPY（默认值）：复制源Object的元数据到目标Object。<br/> *  REPLACE：忽略源Object的元数据，直接采用请求中指定的元数据。文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE | No       |
| X-Ufile-Storage-Class      | String  |                                                              | No       |

Request Elements

说明：未使用。

Responses

Response Headers

| Name           | Type    | Description                    |
| -------------- | ------- | ------------------------------ |
| Content-Type   | String  | 响应body部分的类型             |
| Content-Length | Integer | 响应body部分的长度             |
| ETag           | String  | 已经上传文件在US3中的哈希值    |
| X-SessionId    | String  | 请求失败时返回本次请求的会话Id |

Response Elements

| Name    | Type    | Description          |
| ------- | ------- | -------------------- |
| RetCode | Integer | 执行失败时的错误代码 |
| ErrMsg  | String  | 执行失败时的错误消息 |

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
X-Ufile-Copy-Source: /SourceBucketName/SourceObjectName
```

Example Response:

```
HTTP/1.1 200 OK
Content-Length: 0
ETag: "AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH"
```

Example Response with Error:

```
HTTP/1.1 404 Not Found
Content-Type: applicaton/json
Content-Length: 54 
X-SessionId: e2f4fc84-3936-4a2d-85b5-ef8f2e79933c
X-Ufile-Copy-Source: /SourceBucketName/SourceObjectName

{
    "RetCode": -30010,
    "ErrMsg": "bucket not exist"
}
```

