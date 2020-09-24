# 删除文件 - DeleteFile 

删除文件

Requests

Syntax:

```
DELETE /<file_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```
Request Headers

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|删除请求的授权签名，详情可参考 [UFile API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)  |Yes     |

Request Parameters

说明：未使用。

Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name   |Type   |Description|
| ---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误提示 |

Example

Example Request:

```
DELETE /demofile HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
Example Response:

```
HTTP/1.1 204 NoContent
Content-Length: 0
```
