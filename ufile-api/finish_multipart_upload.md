# 完成分片 - FinishMultipartUpload 

完成分片上传

> 完成分片上传是把之前的各个分片数据块组合成一个文件。由于分片上传适用的文件一般较大，传输耗时较长，等上传完毕开始指定的key可能已经被占用,遇到这种情形时会采用newKey参数的值作为文件最终的key，否则仍然采用原来的key。

Requests

Syntax:

```
POST /<key_name>?uploadId=<upload_id>&newKey=<new_key> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Type: <mimetype>
Content-Length: 63
```
Request Parameters

Request Headers

|Name          |Type   |Description|Required|
|---|---|---|---|
|Authorization |String |上传请求的授权签名  |Yes     |
|Content-Length|Integer|请求body部分的长度|Yes     |
|Content-Type  |String |请求body部分的类型|No      |

Request Elements

说明: 未使用

Responses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|ETag          |String |已上传文件的哈希值       |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name    |Type   |Description        |
|---|---|---|
|Bucket  |String |已上传文件所属Bucket的名称   |
|Key     |String |已上传文件在Bucket中的Key名称|
|FileSize|Integer|已上传文件的大小           |

说明: 同一文件所有已上传分片的ETag用逗号拼接的字符串，作为请求的 body 数据。

Example

Example Request:

```
POST /demokey?uploadId=0f188eb2-5e19-49c3-94c9-36fb5a0ff72a&newKey=anotherkey HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Type: text/plain
Content-Length 287 

9EV6kXgrhTfhy65nHAe84vby2po=,bt5wxJ2fYzAIsklPwAeB7Z9LHQI=,Tt_XCL1oic2KI9xD4Gyxa9g_ht0=,DMmtV-wLenWHa5zP0h24ewlvrsc=,UMEvhZgJZsCXV_jIAOXQC60MakI=,1CTgeZYujKyu9ob13800ndWR3f8=,a1_eDguW8oGbDDBbv9Ru3-lJD20=,Q9IVA8bANo4Fmsd2W3e3iiXQrDU=,MiTIX1Mt4wUbpto2-oZ26dovSek=,MuKlR_GmcZuVRx0YEbJZF4_yBvo=
```
Example Response:

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 79 
ETag: AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH

{
    "Bucket": "demobucket",
    "Key": "anotherkey",
    "FileSize": 41943040
}
```
