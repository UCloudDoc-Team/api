# 绑定SSL证书-BindSSL

将SSL证书绑定到VServer

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|ULBId|string|所绑定ULB实例ID|**Yes**|
|VServerId|string|所绑定VServer实例ID|**Yes**|
|SSLId|string|SSL证书的Id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindSSL
&Region=cn-bj2
&ProjectId=project-xs13ik
&SSLId=ssl-kskl39s
&ULBId=ulb-kix4tp
&VServerId=vserver-9b646b
```

# Response Example
```
{
    "Action": "BindSSLResponse", 
    "RetCode": 0
}
```

