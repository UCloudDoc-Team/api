# 绑定SSL证书-BindCertificate

绑定新的SSL证书到指定域名

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|CertificateID|int|SSL证书ID，可通过DescribeWafDomainCertificateInfo查询|**Yes**|
|FullDomain|string|需要绑定证书的域名，必须与证书同属一个一级域名|**Yes**|
|CertificateName|string|证书名称|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindCertificate
&ProjectId=org-xxx
&CertificateID=901
&FullDomain=www.test.com
```

# Response Example
```
{
    "Action": "BindCertificateResponse", 
    "RetCode": 0
}
```

