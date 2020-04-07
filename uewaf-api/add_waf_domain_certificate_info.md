# 添加SSL证书-AddWafDomainCertificateInfo

添加SSL证书，支持keyless

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|域名|**Yes**|
|CertificateName|string|证书名称|**Yes**|
|SslPublicKey|string|ssl公钥|**Yes**|
|SslMD|string|证书MD5校验值，开启keyless只需要计算公钥的md5|**Yes**|
|SslKeyless|string|keyless开关，默认关闭；可选值：开启(on)，关闭(off)|**Yes**|
|SslPrivateKey|string|ssl私钥，开启keyless不需要赋值|No|
|SslKeyServer|string|SSL key server地址，格式为ip:端口,192.168.23.66:5263|No|
|SslKeylessCertFileName|string|Keyless上传证书的文件名称|No|
|SslKeylessCertFileData|string|Keyless上传证书文件的内容，base64编码|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功返回的SSL证书ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafDomainCertificateInfo
&ProjectId=org-xxx
&Domain=www.test.com
&CertificateName=test
&SslPublicKey=LS0tLS1CRUdJTiBDFURS0tLS0tCk1JSUZyRENDQkpTZ0F3SUJBZ0lRQW
&SslPrivateKey=LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFb3dJQkFBS
&SslMD=617d723ec99fa0a4132a9a54052d4cd6
&SslKeyLess=off

```

# Response Example
```
{
    "Action": "AddWafDomainCertificateInfoResponse", 
    "RetCode": 0, 
    "Id": 6
}
```

