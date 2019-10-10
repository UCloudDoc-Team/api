# 绑定PathX SSL证书-BindPathXSSL

绑定PathX SSL证书

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|SSLId|string|证书ID，如果没有指定证书ID也没有申请免费证书，HTTPS接入无法正常工作|**Yes**|
|UGAId|string|UGA实例ID|**Yes**|
|Port.n|int|绑定SSL证书的HTTPS端口。Port.0 Port.1对应多个Port。如果Port不存在则不会绑定|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindPathXSSL
&ProjectId=NIDztWip
&SSLId=IjRdcFgz
&UGAId=KDytIAQR
&Port.n=KLfjgsZc
```

# Response Example
```
{
    "Action": "BindPathXSSLResponse", 
    "RetCode": 0
}
```

