# 显示域名对应的证书-DescribeWafDomainCertificateInfo

显示域名对于的证书

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要查询域名，为空时查找所有|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|证书数量|No|
|CertificateInfo|object|证书详情列表，参考DoaminCertificateInfo|No|

## DoaminCertificateInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CertificateID|int|证书ID|No|
|CertificateName|string|证书名称|No|
|Domain|string|证书一级域名|No|
|UploadTime|object|证书入库时间，utc时间格式，如：2020-02-06T18:46:17+08:00|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainCertificateInfo
&ProjectId=org-xxx
&Domain=www.test.com
```

# Response Example
```
{
    "Action": "DescribeWafDomainCertificateInfoResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "CertificateInfo": [
        {
            "Domain": "test.com", 
            "CertificateID": 834, 
            "CertificateName": "test", 
            "UploadTime": "2020-02-06T18:46:17+08:00"
        }
    ]
}
```

