# 删除SSL证书-DeleteSSL

删除SSL证书

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|SSLId|string|SSL证书的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteSSL
&Region=cn-bj2
&ProjectId=project-xs13ik
&SSLId=ssl-s1v2e0
```

# Response Example
```
{
    "Action": "DeleteSSLResponse", 
    "RetCode": 0
}
```

