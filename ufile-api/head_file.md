====== 查询文件基本信息 - HEADFile ======
{{indexmenu_n>50}}

查询文件基本信息

Requests

Syntax:

<code>
HEAD /<file_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token> 
</code>
Request Parameters

Request Headers

^Name         ^Type  ^Description^Required^
|Authorization|String|下载请求的授权签名  |No      |

Request Elements

说明: 未使用。

Responses

Response Headers

^Name          ^Type   ^Description     ^
|Content-Type  |String |请求下载文件的类型       |
|Content-Length|Integer|请求下载文件的长度       |
|Content-Range |String |请求下载文件的范围       |
|ETag          |String |请求下载文件在UFile的哈希值|
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

^Name   ^Type   ^Description^
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误提示 |

> 注意: 成功下载时只返回HTTP 200回应和数据体。

Example

Example Request:

<code>
HEAD /demofile HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
</code>
Example Response:

<code>
HTTP/1.1 200 OK
ETag: c5371fe3624d438cd8a59420a3221978
Content-Type: image/jpg
Content-Length: 1234
</code>
