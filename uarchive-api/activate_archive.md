# 激活文件 - ActivateArchive 

激活待下载文件

# Requests Syntax

```
POST /ArchiveName?activate HTTP/1.1
Host: <vault_name>.uarchive.ucloud.cn
Authorization: <token>
```

# Request Headers

|Parameter name|Type  |Description                          |Required|
|---|---|---|---|
|Authorization    |String|激活请求的授权签名                 |Yes     |

# Request Elements

|Name      |Type   |Description            |
|---|---|---|
|VaultName    |String |Vault空间名称                   |
|ArchiveName   |Integer |Vault中文件的名称            |Yes     |

# Response Headers

|Parameter name|Type  |Description                          |
|---|---|---|
|Content-Length    |Integer |响应body部分的长度                 |
|X-SessionId    |String |请求失败时返回本次请求的会话Id                 |

# Response Elements

|Name      |Type   |Description            |
|---|---|---|
|RetCode   |Integer |执行失败时的错误码         |
|ErrMsg   |String |执行失败时的错误消息           |

注意: 成功执行只会返回HTTP 200回应,不带body数据

# Example

## Example Request:
```
POST /testarchive?activate= HTTP/1.1
Host: demoVault.uarchive.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Accept-Encoding: gzip
```

## Example Response:
```
HTTP/1.1 200 OK
Content-Length: 0
Content-Type: text/plain
```
