# 文件存储类型转换 - ClassSwitch 

## 简介

用于转换文件的存储类型，可以由热转冷。如标准->低频/归档, 低频->归档

## 定义

### 句法（Syntax）:

```
PUT /<object_name>?storageClass=<storage_class> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```
### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|存储类型转换请求的授权签名，详情可参考 [API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |Yes     |

**Request Elements（请求元素）**

|Name    |Type  |Description          |Required|
|---|---|---|---|
|storageClass    |String|目标存储类型，三种：IA（低频）、ARCHIVE（冷存）|Yes     |

### 响应（Responses）

**响应头（Response Headers）**

|Name          |Type   |Description     |
|---|---|---|
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

**响应元素（Response Elements）**

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误码  |
|ErrMsg |String |执行失败时的错误消息 |

> 注意: 成功执行只会返回HTTP 200回应,不带body数据.

## 示例

### 请求示例（Example Request）:

```
PUT /standard_file.txt?storageClass=IA HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
### 响应示例（Example Response）:

```
HTTP/1.1 200 OK
Content-Length: 0
```

### 响应错误示例（Example Response with Error）:

```
HTTP/1.1 403 Forbidden
Content-Type: applicaton/json
Content-Length: 62
X-SessionId: e2f4fc84-3936-4a2d-85b5-ef8f2e79933c
{
    "RetCode": -148660,
    "ErrMsg": "switch class not allowed"
}
```
