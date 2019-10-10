# 解绑PathX SSL 证书-UnBindPathXSSL

解绑PathX SSL 证书

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|UGA实例ID。|**Yes**|
|SSLId|string|SSL证书ID。|**Yes**|
|Port.n|int|解绑SSL证书的HTTPS端口。Port.0 Port.1格式 端口错误则解绑失败。|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UnBindPathXSSL
&ProjectId=GAULtRoE
&UGAId=IYVJijDo
&SSLId=lgsPtIQD
&Port.n=NnzdSpln
```

# Response Example
```
{
    "Action": "UnBindPathXSSLResponse", 
    "RetCode": 0
}
```

