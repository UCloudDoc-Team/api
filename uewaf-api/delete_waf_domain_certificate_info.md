# 删除指定域名的ssl证书-DeleteWafDomainCertificateInfo

删除指定域名的ssl证书

!> 证书在使用中不允许删除

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|CertificateID|int|要删除的证书ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafDomainCertificateInfo
&CertificateID=6
&ProjectId=sLfetaSg
```

# Response Example
```
{
    "Action": "DeleteWafDomainCertificateInfoResponse", 
    "RetCode": 0
}
```

