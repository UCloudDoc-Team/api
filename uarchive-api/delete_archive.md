====== 删除文件 - DeleteArchive ======
{{indexmenu_n>15}}

删除文件

#Requests Syntax

<code>
DELETE /<Archive_name> HTTP/1.1
Host: <Vault_name>.uarchive.ucloud.cn
Authorization: <token>
</code>

#Request Headers

^Parameter name^Type  ^Description                          ^Required^
|Authorization    |String|删除请求的授权签名                 |Yes     |

#Response Headers

^Parameter name^Type  ^Description                          ^
|Content-Length    |Integer |响应body部分的长度                 |
|X-SessionId    |String |请求失败时返回本次请求的会话Id                 |

#Response Elements

^Name      ^Type   ^Description            ^
|RetCode   |Integer |执行失败时的错误码         |
|ErrMsg   |String |执行失败时的错误消息           |

#Example

##Example Request:

<code>
DELETE /demoArchive HTTP/1.1
Host: demoVault.uarchive.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
</code>

##Example Response:

<code>
HTTP/1.1 204 NoContent
Content-Length: 0
</code>