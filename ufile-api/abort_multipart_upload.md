====== 放弃分片 - AbortMultipartUpload ======
{{indexmenu_n>75}}

放弃分片上传

Requests

Syntax:

<code>
DELETE /<key_name>?uploadId=<upload_id> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
</code>
注意：一旦放弃分片上传，就不能再使用前面的upload_id做任何操作，已经上传的数据也会被删除。如果一个文件的所有分片未全部上传，又未执行放弃分片上传，则已上传分片会在一定时间后删除。

Request Parameters

Request Headers

^Name         ^Type  ^Description^Required^
|Authorization|String|上传请求的授权签名  |Yes     |

Request Elements

说明：未使用。

Responses

Response Headers

^Name          ^Type   ^Description     ^
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

说明：未使用。

Example

Example Request:

<code>
DELETE /demokey?uploadId=0f188eb2-5e19-49c3-94c9-36fb5a0ff72a HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
</code>
Example Response:

<code>
HTTP/1.1 200 OK
</code>
