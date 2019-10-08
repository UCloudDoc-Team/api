====== 下载文件 - DownloadArchive ======
{{indexmenu_n>20}}

下载文件

#Requests Syntax

<code>
GET /<Archive_name> HTTP/1.1
Host: <Vault_name>.uArchive.ucloud.cn
Authorization: <token> 
Range: bytes=byte_range
If-Modified-Since: <timestamp>
</code>

#Request Headers

^Parameter name^Type  ^Description                          ^Required^
|Authorization    |String|下载请求的授权签名                 |Yes     |

#Response Headers

^Parameter name^Type  ^Description                          ^
|Content-Type    |String |请求下载文件的类型                |
|Content-Length    |Integer |请求下载文件的长度                 |
|ETag    |String |请求下载文件在UArchive的哈希值                |
|X-SessionId    |String |请求失败时返回本次请求的会话Id                 |

#Response Elements

^Name      ^Type   ^Description            ^
|RetCode   |Integer |执行失败时的错误码         |
|ErrMsg   |String |执行失败时的错误消息           |

注意: 成功执行只会返回HTTP 200回应和数据体

#Example

##Example Request:
<code>
GET /demoArchive HTTP/1.1
Host: demoVault.uarchive.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
</code>

##Example Response:
<code>
HTTP/1.1 200 OK
ETag: c5371fe3624d438cd8a59420a3221978
Content-Type: image/jpg
Content-Length: 1234

<data>
</code>

Example Response Only Get Partial Content:
<code>
HTTP/1.1 206 Partial Content
Content-Type: image/jpg
Content-Length: 34
Content-Range: bytes 0-10/34

<data>
</code>