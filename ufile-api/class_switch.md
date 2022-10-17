# 文件存储类型转换 - ClassSwitch 

说明：用于转换文件的存储类型，可以任意转换文件为标准、低频、冷存三种存储类型，注意：冷存文件如果想转换为其他两种类型必须在解冻期内。

Requests

Syntax:

```
PUT /<object_name>?storageClass=<storage_class> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```
Request Parameters

Request Headers

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|存储类型转换请求的授权签名，详情可参考 [API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |Yes     |

Request Elements

|Name    |Type  |Description          |Required|
|---|---|---|---|
|storageClass    |String|目标存储类型，三种：STANDARD（标准）、IA（低频）、ARCHIVE（冷存）|Yes     |

Reponses

Response Headers

|Name          |Type   |Description     |
|---|---|---|
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误码  |
|ErrMsg |String |执行失败时的错误消息 |

> 注意: 成功执行只会返回HTTP 200回应,不带body数据.

Example

Example Request:

```
PUT /archive_file.txt?storageClass=IA HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
Example Response:

```
HTTP/1.1 200 OK
Content-Length: 0
```

Example Response with Error:

```
HTTP/1.1 403 Forbidden
Content-Type: applicaton/json
Content-Length: 62
X-SessionId: e2f4fc84-3936-4a2d-85b5-ef8f2e79933c
{
    "RetCode": -148671,
    "ErrMsg": "file has not been restored"
}
```
