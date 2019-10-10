# 获取SSL证书信息-DescribePathXSSL

获取SSL证书信息,支持分页，支持按证书名称 证书域名模糊搜索

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|SSLId|string|SSL证书的Id，不传分页获取证书列表|No|
|SearchValue|string|不为空则按证书名称、证书域名模糊搜索 分页返回结果|No|
|Limit|int|最大返回条数，默认100，最大400|No|
|Offset|int|偏移值 默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|SSL证书详细信息，具体结构见 PathXSSLSet|No|
|TotalCount|int|符合条件的证书总数|No|

## PathXSSLSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SSLId|string|SSL证书的Id|No|
|SSLName|string|SSL证书的名字|No|
|SubjectName|string|证书域名|No|
|ExpireTime|int|证书过期时间 时间戳|No|
|SourceType|int|证书来源，0：用户上传 1: 免费颁发|No|
|SSLMD5|string|SSL证书（用户证书、私钥、ca证书合并）内容md5值|No|
|CreateTime|int|SSL证书的创建时间 时间戳|No|
|SSLBindedTargetSet|array|SSL证书绑定的对象|No|
|SSLContent|string|SSL证书内容|No|

## SSLBindedTargetSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ResourceId|string|SSL证书绑定到的实例ID|**Yes**|
|ResourceName|string|SSL证书绑定到的实例名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePathXSSL
&Region=cn-zj
&ProjectId=BhxrYOhJ
&SSLId=qfAwKRCy
&Limit=CwxhOhHj
&Offset=xFymEXUY
&SearchValue=CwubhZXD
&Limit=4
&Offset=2
```

# Response Example
```
{
    "Action": "DescribePathXSSLResponse", 
    "TotalCount": 8, 
    "RetCode": 0, 
    "DataSet": [
        {
            "SSLName": "bTXXQWOI", 
            "SSLBindedTargetSet": [
                {
                    "VServerId": "HJsHxIXH", 
                    "VServerName": "hXJjEamx", 
                    "ULBId": "iFrUItFj", 
                    "ULBName": "nfuWqqyI"
                }
            ], 
            "SSLType": "PxRwdLNI", 
            "SSLContent": "mwWAXoAn", 
            "SSLId": "tddMiqYh", 
            "CreateTime": 6
        }
    ]
}
```

