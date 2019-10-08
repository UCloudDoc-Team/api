====== 初始化分片 - InitiateMultipartUpload ======
{{indexmenu_n>60}}

初始化分片上传

Requests

Syntax:

<code>
POST /<key_name>?uploads HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Length: 0
</code>
Request Parameters

Request Headers

^Name          ^Type   ^Description^Required^
|Authorization |String |上传请求的授权签名  |Yes     |
|Content-Length|Integer|请求body部分的长度|No      |
| X-Ufile-Storage-Class   | String   | 文件存储类型，分别是标准、低频、归档，对应有效值：STANDARD, IA, ARCHIVE                            | No        |

Request Elements

说明：未使用。

Responses

Response Headers

^Name          ^Type   ^Description     ^
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

^Name    ^Type   ^Description       ^
|UploadId|String |本次分片上传的上传Id       |
|BlkSize |Integer|分片的块大小            |
|Bucket  |String |上传文件所属Bucket的名称   |
|Key     |String |上传文件在Bucket中的Key名称|

Example

Example Request:

<code>
POST /demokey?uploads HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Length: 0
</code>
Example Response:

<code>
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 121

{
    "UploadId": "0f188eb2-5e19-49c3-94c9-36fb5a0ff72a",
    "BlkSize": 4194304,
    "Bucket": "demobucket",
    "Key": "demokey"
}
</code>
