====== 前缀列表查询 - GetArchiveList ======
{{indexmenu_n>50}}

获取Vault中指定文件前缀的文件列表

#Requests Syntax

<code>
GET /?list&prefix=<prefix>&marker=<marker>&limit=<limit>
Host: <Vault_name>.uarchive.ucloud.cn
Authorization: <token> 
</code>

#Request Headers

^Parameter name^Type  ^Description                          ^Required^
|prefix    |String|前缀，utf-8编码，默认为空字符串                 |     |
|marker    |String|标志字符串，utf-8编码，默认为空字符串                 |     |
|limit    |Integer|文件列表数目，默认为20                 |     |
|Authorization    |String|下载请求的授权签名                 |     |

#Response Elements

^Name      ^Type   ^Description            ^
|VaultName   |String |Vault的名称         |
|VaultId   |String |Vault的ID           |
|NextMarker   |String |下一个标志字符串，utf-8编码         |
|DataSet  |Array |文件列表           |

##DataSet Item

^Name      ^Type   ^Description            ^
|VaultName   |String |文件所属Vault名称        |
|Key   |String |文件名称,utf-8编码           |
|Hash   |String |文件hash值         |
|MimeType   |Array |文件mimetype           |
|Size   |Integer |文件大小         |
|CreateTime   |Integer |文件创建时间           |
|ModifyTime  |Integer |文件修改时间           |

#Example

##Example Request:
<code>
GET /?list&prefix=aaa
Host: blue.uarchive.ucloud.cn
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
</code>

##Example Response:
<code>
{
    "VaultName": "blue",
    "VaultId": "uarchive-qs20fr",
    "NextMarker": "",
    "DataSet": [
        {
            "VaultName": "blue",
            "Key": "aaa.jpg",
            "Hash": "fbfc1aba39fdac0e0f298461970529d3",
            "MimeType": "image/jpeg",
            "Size": 344500,
            "CreateTime": 1408298579,
            "ModifyTime": 1408298579
       }
    ]
}
</code>