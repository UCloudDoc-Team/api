# 删除Vault-DeleteVault

删除Vault

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不选择为默认项目，子帐号必选|No|
|VaultName|string|待删除Vault的名称|**Yes**|

```
特别说明:
VaultName参数必须符合Vault名称规范,规范如下: (1) 长度在3~63字节之间； (2) 可以由多个标签
组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结
尾的字符只能是小写字母或数字； (3) 不可以是IP地址。

```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VaultName|string|已创建Vault的名称|No|
|VaultId|string|已创建Vault的ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteVault
&VaultName=blue
&ProjectId=WIpvovJc
```

# Response Example
```
{
    "Action": "DeleteVaultResponse", 
    "VaultName": "blue", 
    "VaultId": "uarchive-xxx", 
    "Retcode": 0
}
```

