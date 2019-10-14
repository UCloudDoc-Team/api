# 获取Vault信息-DescribeVault

获取Vault信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不选择为默认项目，子帐号必选|No|
|VaultName|string|待获取Vault的名称，若不提供，则获取所有Vault|**Yes**|
|Offset|int|获取所有Vault列表的偏移数目，默认为0|No|
|Limit|int|获取所有Vault列表的限制数目，默认为20|No|

?> 特别说明:
VaultName参数必须符合Vault名称规范,规范如下: (1) 长度在3~63字节之间； (2) 可以由多个标签组成，各个标签用 . 间隔，每个标签只能包含小字母、数字、连接符（短横线），并且标签的开头和结尾的字符只能是小写字母或数字； (3) 不可以是IP地址。

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|Vault的描述信息|No|

## VaultSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|VaultName|string|Vault名称|**Yes**|
|VaultId|string|Vault的ID|**Yes**|
|Domain|string|Vault的域名集合|**Yes**|
|CreateTime|int|Vault的创建时间|**Yes**|
|ModifyTime|int|Vault的修改时间|**Yes**|
|Region|string|Vault所属地域|**Yes**|

# Request Example
```
https://api.ucloud.cn?Action=DescribeVault
&VaultName=blue
&Offset=0
&Limit=20
&ProjectId=cOoJjcam
```

# Response Example
```
{
    "Action": "DescribeVaultResponse", 
    "DataSet": [
        {
            "Domain": "robert-test.uarchive.ucloud.cn", 
            "Region": "cn-bj", 
            "VaultName": "robert-test", 
            "VaultId": "uarchive-xxx", 
            "ModifyTime": 1468929616, 
            "CreateTime": 1468929616
        }
    ]
}
```

