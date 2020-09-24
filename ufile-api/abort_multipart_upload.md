# 放弃分片 - AbortMultipartUpload 

放弃分片上传

Requests

Syntax:

```
DELETE /<key_name>?uploadId=<upload_id> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```
注意：一旦放弃分片上传，就不能再使用前面的upload_id做任何操作，已经上传的数据也会被删除。如果一个文件的所有分片未全部上传，又未执行放弃分片上传，则已上传分片会在一定时间后删除。

Request Parameters

Request Headers

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|上传请求的授权签名，详情可参考 [UFile API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |Yes     |

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

说明：未使用。

Example

Example Request:

```
DELETE /demokey?uploadId=0f188eb2-5e19-49c3-94c9-36fb5a0ff72a HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
Example Response:

```
HTTP/1.1 200 OK
```
