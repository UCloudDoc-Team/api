# 删除文件 - DeleteFile 

## 简介

删除文件

## 定义

### 句法（Syntax）:

```
DELETE /<object_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
```

### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|删除请求的授权签名，详情可参考 [API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)  |Yes     |

**请求元素（Request Elements）**

> 说明：未使用。

### 响应（Responses）

**响应头（Response Headers）**

|Name          |Type   |Description     |
|---|---|---|
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

**响应元素（Response Elements）**

|Name   |Type   |Description|
| ---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误提示 |

## 示例

### 请求示例（Example Request）:

```
DELETE /demofile HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
### 响应示例（Example Response）:

```
HTTP/1.1 204 NoContent
Content-Length: 0
```
