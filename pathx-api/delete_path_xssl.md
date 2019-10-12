# 删除PathX SSL证书-DeletePathXSSL

删除PathX SSL证书

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SSLId|string|SSL证书的ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeletePathXSSL
&ProjectId=org-xxx
&SSLId=gssl-xxx
```

# Response Example
```
{
    "Action": "DeletePathXSSLResponse", 
    "RetCode": 0
}
```

