# 查询文件基本信息 - HeadFile 

## 简介
查询文件基本信息

## 定义

### 句法（Syntax）:


```
HEAD /<object_name> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token> 
```

### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Name         |Type  |Description|Required|
|---|---|---|---|
|Authorization|String|下载请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)   |No      |


**请求元素（Request Elements）**

> 说明: 未使用。

### 响应（Responses）

**响应头（Response Headers）**

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |请求下载文件的类型       |
|Content-Length|Integer|请求下载文件的长度       |
|Content-Range |String |请求下载文件的范围       |
|ETag          |String |请求下载文件在US3的哈希值|
|X-SessionId   |String |请求失败时返回本次请求的会话Id|
|X-Ufile-Meta- *   |String |US3中规定所有以X-Ufile-Meta-为前缀的参数视为用户自定义元数据（User Meta），比如x-ufile-meta-location。一个文件可以有多个类似的参数，但所有的User Meta总大小不能超过8KB。这些User Meta信息会在GetFile或者HeadFile的时候在HTTP头部中返回。|

**响应元素（Response Elements）**

|Name   |Type   |Description|
|---|---|---|
|RetCode|Integer|执行失败时的错误代码 |
|ErrMsg |String |执行失败时的错误提示 |

> 注意: 成功下载时只返回HTTP 200回应和数据体。

## 示例

### 请求示例（Example Request）:

```
HEAD /demofile HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
```
### 响应示例（Example Response）:

```
HTTP/1.1 200 OK
ETag: "c5371fe3624d438cd8a59420a3221978"
Content-Type: image/jpg
Content-Length: 1234
```
