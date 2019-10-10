# 获取全球加速线路信息-DescribePathXLineConfig

获取全球加速线路信息

# Request Parameters

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|LineSet|array|UGAA线路列表|No|

## UGAALine
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LineFrom|string|线路源|**Yes**|
|LineTo|string|线路目的|**Yes**|
|LineId|string|线路计费Id|No|
|LineFromName|string|线路源中文名称|**Yes**|
|LineToName|string|线路目的中文名称|**Yes**|
|LineDetail|array|子线路信息|No|

## LineDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|LineId|string||No|
|ResourceId|string||No|
|Bandwidth|int||No|
|State|string||No|
|ChargeType|string||No|
|CreateTime|int||No|
|ExpireTime|int||No|
|Expire|bool||No|
|PayMode|string||No|
|Endpoints|array||No|

## VpcDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域|No|
|EndpointId|string|Endpoint ID|No|
|ResourceId|string|接入资源ID|No|
|Vendor|string|云商|No|
|VPCId|string|接入点VPC ID|No|
|VPCName|string|接入点VPC名称|No|
|Networks|array|VPC网段|No|
|ChargeType|string|付费方式|No|
|CreateTime|int|创建时间|No|
|ExpireTime|int|过期时间|No|
|Mode|string|接入方式|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribePathXLineConfig
```

# Response Example
```
{
    "Action": "DescribePathXLineConfigResponse", 
    "LineSet": [
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineFrom": "cn-bj2", 
            "LineTo": "ge-fra", 
            "LineToName": "\u6b27\u6d32", 
            "LineId": "line_cn-bj2_ge-fra"
        }, 
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineFrom": "cn-bj2", 
            "LineTo": "us-ca", 
            "LineToName": "\u5317\u7f8e", 
            "LineId": "line_cn-bj2_us-ca"
        }, 
        {
            "LineFromName": "\u4e2d\u56fd", 
            "LineFrom": "cn-gd", 
            "LineTo": "hk", 
            "LineToName": "\u4e9a\u592a", 
            "LineId": "line_cn-gd_hk"
        }, 
        {
            "LineFromName": "\u4fc4\u7f57\u65af", 
            "LineFrom": "ge-fra2", 
            "LineTo": "us-ca2", 
            "LineToName": "\u5317\u7f8e", 
            "LineId": "line_ge-fra2_us-ca2"
        }, 
        {
            "LineFromName": "\u6b27\u6d32", 
            "LineFrom": "ge-fra", 
            "LineTo": "cn-bj2", 
            "LineToName": "\u4e2d\u56fd", 
            "LineId": "line_ge-fra_cn-bj2"
        }, 
        {
            "LineFromName": "\u4e9a\u592a", 
            "LineFrom": "hk", 
            "LineTo": "cn-gd", 
            "LineToName": "\u4e2d\u56fd", 
            "LineId": "line_hk_cn-gd"
        }, 
        {
            "LineFromName": "\u5317\u7f8e", 
            "LineFrom": "us-ca", 
            "LineTo": "cn-bj2", 
            "LineToName": "\u4e2d\u56fd", 
            "LineId": "line_us-ca_cn-bj2"
        }, 
        {
            "LineFromName": "\u4e2d\u56fd\u591a\u5730", 
            "LineTo": "us-ca", 
            "LineToName": "\u5317\u7f8e", 
            "LineFrom": "cn-multi", 
            "LineDetail": [
                {
                    "LineFromName": "\u4e9a\u592a", 
                    "LineFrom": "hk", 
                    "LineTo": "cn-gd", 
                    "LineToName": "\u4e2d\u56fd", 
                    "LineId": "line_hk_cn-gd"
                }, 
                {
                    "LineFromName": "\u5317\u7f8e", 
                    "LineFrom": "us-ca", 
                    "LineTo": "cn-bj2", 
                    "LineToName": "\u4e2d\u56fd", 
                    "LineId": "line_us-ca_cn-bj2"
                }
            ], 
            "LineId": "line_us-ca_cn-multi"
        }
    ], 
    "RetCode": 0
}
```

