# 创建证书-CreatePathXSSL

创建SSL证书，可以把整个 Pem 证书内容传到SSLContent，或者把证书、私钥、CA证书分别传过来

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SSLName|string|SSL证书的名字，默认值为空|**Yes**|
|SSLType|string|所添加的SSL证书类型，目前只支持Pem格式|No|
|SSLContent|string|SSL证书的完整内容，私钥不可使用密码，包括加密证书的私钥、用户证书或CA证书等|No|
|UserCert|string|用户自签证书内容|No|
|PrivateKey|string|加密证书的私钥，不可使用密码保护，开启密码保护后，重启服务需要输入密码|No|
|CACert|string|CA颁发证书内容|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SSLId|string|SSL证书的Id|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreatePathXSSL
&Region=cn-zj
&ProjectId=UljFulPk
&SSLName=nASNpGFg
&SSLType=sKorsKNf
&SSLContent=XVhRxjyG
&UserCert=YvFTkDmc
&PrivateKey=gZdziLxN
&CaCert=taXtiarS
```

# Response Example
```
{
    "Action": "CreatePathXSSLResponse", 
    "SSLId": "acApKlzr", 
    "RetCode": 0
}
```

