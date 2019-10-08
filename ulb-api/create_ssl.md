# 创建SSL证书-CreateSSL

创建SSL证书，可以把整个 Pem 证书内容传过来，或者把证书、私钥、CA证书分别传过来

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|SSLName|string|SSL证书的名字，默认值为空|**Yes**|
|SSLType|string|所添加的SSL证书类型，目前只支持Pem格式|No|
|SSLContent|string|SSL证书的完整内容，包括用户证书、加密证书的私钥、CA证书|No|
|UserCert|string|用户的证书|No|
|PrivateKey|string|加密证书的私钥|No|
|CaCert|string|CA证书|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SSLId|string|SSL证书的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateSSL
&Region=cn-bj2
&ProjectId=project-xs13ik
&SSLName=new-ssl
&SSLContent=-----BEGIN&nbspRSA&nbspPRIVATE&nbspKEY-----xxx
```

# Response Example
```
{
    "Action": "CreateSSLResponse", 
    "SSLId": "ssl-s1v2e0", 
    "RetCode": 0
}
```

