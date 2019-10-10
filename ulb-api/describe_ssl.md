# 获取SSL证书信息-DescribeSSL

获取SSL证书信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SSLId|string|SSL证书的Id|No|
|Limit|int|数据分页值，默认为20|No|
|Offset|int|数据偏移量，默认值为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的SSL证书总数|No|
|DataSet|array|SSL证书详细信息，具体结构见 ULBSSLSet|No|

## ULBSSLSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SSLId|string|SSL证书的Id|No|
|SSLName|string|SSL证书的名字|No|
|SSLType|string|SSL证书类型，暂时只有 Pem 一种类型|No|
|SSLContent|string|SSL证书的内容|No|
|CreateTime|int|SSL证书的创建时间|No|
|SSLBindedTargetSet|array|SSL证书绑定到的对象|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeSSL
&Region=cn-bj2
&ProjectId=project-XXXXXX
```

# Response Example
```
{
    "Action": "DescribeSSLResponse", 
    "DataSet ": [
        {
            "SSLName": "testpem", 
            "HashValue": "1d5da9cf215d7c0e7b41b85af8adac2b", 
            "SSLType": "Pem", 
            "VServerId": "", 
            "SSLContent": "-----BEGIN RSA PRIVATE KEY-----\nXXXXXXXXXXXXX\n-----END CERTIFICATE-----", 
            "SSLId": "ssl-XXXXX", 
            "CreateTime": 1418099063
        }
    ], 
    "RetCode": 0, 
    "TotalCount": 1
}
```

