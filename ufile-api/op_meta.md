# 操作文件的Meta信息 - OpMeta 

## 简介

操作文件的Meta信息

## 定义

### 句法（Syntax）:

```
POST /<object_name>?opmeta HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
Content-Type: application/json
Content-Length: <length>

 {
     "op": <op-type>,
     "metak": <meta-key>,
     "metav": <meta-value>
 }
```
> 说明： 目前本接口限定 op: "set" 和 metak: "mimetype"，即仅允许设置文件的mimetype。

### 请求参数（Request Parameters）

**请求头（Request Headers）**

|Name          |Type   |Description|Required|
|---|---|---|---|
|Authorization |String |请求的授权签名，[API 签名算法](https://docs.ucloud.cn/ufile/api/authorization?id=%e6%96%87%e4%bb%b6%e7%ae%a1%e7%90%86%e7%ad%be%e5%90%8d%e7%ae%97%e6%b3%95)     |Yes     |
|Content-Length|Integer|请求body部分的长度|Yes     |
|Content-Type  |String |请求body部分的类型|Yes     |

**请求元素（Request Elements）**

> 说明: 未使用

### 响应（Responses）

**响应头（Response Headers）**

|Name          |Type   |Description     |
|---|---|---|
|Content-Type  |String |响应body部分的类型     |
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

**响应元素（Response Elements）**

> 说明: 未使用

## 示例

### 请求示例（Example Request）:

```
POST /demoobject?opmeta HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Type: application/json
Content-Length 53

{
    "op": "set",
    "metak": "mimetype",
    "metav": "text/plain"
} 
```
### 响应示例（Example Response）:

```
HTTP/1.1 200 OK
Content-Length: 0
```
