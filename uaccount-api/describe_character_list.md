# 获取角色列表-DescribeCharacterList

获取角色列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Offset|int|角色列表的偏移量，默认为0|No|
|Limit|int|角色列表的最大数量，默认为20|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|CharacterSet|array|JSON格式的角色列表实例，每项参数参见下面的 ResponseItem|**Yes**|
|TotalCount|int|角色总数|**Yes**|

## CharacterSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CharacterId|string|角色ID|**Yes**|
|CharacterName|string|角色名|**Yes**|
|CharacterDescription|string|角色描述|**Yes**|
|Modifiable|bool|可修改性|**Yes**|
|PermissionSet|array|权限列表|**Yes**|

## PermissionSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Add|array|有增权限的产品列表|**Yes**|
|Del|array|有删权限的产品列表|**Yes**|
|Mod|array|有改权限的产品列表|**Yes**|
|Get|array|有查权限的产品列表|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeCharacterList
&Offset=7
&Limit=7
```

# Response Example
```
{
    "Action": "DescribeCharacterListResponse", 
    "TotalCount": 2, 
    "CharacterSet": [
        {
            "CharacterName": "Admin", 
            "PermissionSet": {
                "Add": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST", 
                    "ULB", 
                    "UMARKET", 
                    "UMEM", 
                    "UNET", 
                    "USEC", 
                    "UVIDEO", 
                    "UHADOOP", 
                    "UKAFKA", 
                    "UDW", 
                    "UDSET", 
                    "UAI", 
                    "UAI-TRAINING", 
                    "ULIVE", 
                    "UDOCKER", 
                    "UHUB", 
                    "UWAF", 
                    "UDDB", 
                    "UHIDS", 
                    "DBAUDIT", 
                    "UK8S", 
                    "PATHX", 
                    "UKMS", 
                    "UES", 
                    "UFLINK"
                ], 
                "Get": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST", 
                    "ULB", 
                    "UMARKET", 
                    "UMEM", 
                    "UNET", 
                    "USEC", 
                    "UVIDEO", 
                    "UHADOOP", 
                    "UKAFKA", 
                    "UDW", 
                    "UDSET", 
                    "UAI", 
                    "UAI-TRAINING", 
                    "ULIVE", 
                    "UDOCKER", 
                    "UHUB", 
                    "UWAF", 
                    "UDDB", 
                    "UHIDS", 
                    "DBAUDIT", 
                    "UK8S", 
                    "PATHX", 
                    "UKMS", 
                    "UES", 
                    "UFLINK"
                ], 
                "Del": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST", 
                    "ULB", 
                    "UMARKET", 
                    "UMEM", 
                    "UNET", 
                    "USEC", 
                    "UVIDEO", 
                    "UHADOOP", 
                    "UKAFKA", 
                    "UDW", 
                    "UDSET", 
                    "UAI", 
                    "UAI-TRAINING", 
                    "ULIVE", 
                    "UDOCKER", 
                    "UHUB", 
                    "UWAF", 
                    "UDDB", 
                    "UHIDS", 
                    "DBAUDIT", 
                    "UK8S", 
                    "PATHX", 
                    "UKMS", 
                    "UES", 
                    "UFLINK"
                ], 
                "Mod": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST", 
                    "ULB", 
                    "UMARKET", 
                    "UMEM", 
                    "UNET", 
                    "USEC", 
                    "UVIDEO", 
                    "UHADOOP", 
                    "UKAFKA", 
                    "UDW", 
                    "UDSET", 
                    "UAI", 
                    "UAI-TRAINING", 
                    "ULIVE", 
                    "UDOCKER", 
                    "UHUB", 
                    "UWAF", 
                    "UDDB", 
                    "UHIDS", 
                    "DBAUDIT", 
                    "UK8S", 
                    "PATHX", 
                    "UKMS", 
                    "UES", 
                    "UFLINK"
                ]
            }, 
            "Modifiable": false, 
            "CharacterId": "Admin", 
            "CharacterDescription": "\u7ba1\u7406\u5458"
        }, 
        {
            "CharacterName": "test", 
            "PermissionSet": {
                "Add": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST"
                ], 
                "Get": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST"
                ], 
                "Del": [
                    "HYBRID", 
                    "PHOST", 
                    "UCDN", 
                    "UDB", 
                    "UDDP", 
                    "UDISK", 
                    "UFILE", 
                    "UHOST"
                ], 
                "Mod": null
            }, 
            "Modifiable": true, 
            "CharacterId": "lptabl", 
            "CharacterDescription": ""
        }
    ], 
    "RetCode": 0
}
```

