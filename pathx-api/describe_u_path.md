# 获取加速线路信息-DescribeUPath

获取加速线路信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UPathId|string|如果不填参数 返回 ProjectId 下所有的线路资源，填此参数则返回upath实例ID匹配的线路|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UPathSet|array|线路信息数组|**Yes**|

## UPathInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ChargeType|string|计费模式，默认为Month 按月收费,可选范围['Month','Year','Dynamic']|No|
|Name|string|UPath实例名字|No|
|UPathId|string|UPath加速线路实例ID|No|
|Bandwidth|int|带宽，单位Mbps|No|
|LineId|string|选择的线路|No|
|UGAList|array|与该UPath绑定的UGA列表|No|
|CreateTime|int|UPath创建的时间，10位时间戳|No|
|ExpireTime|int|UPath的过期时间，10位时间戳|No|
|LineFromName|string|线路入口名称|No|
|LineToName|string|线路出口名称|No|
|OutPublicIpList|array|线路出口IP数组|No|

## PathXUGAInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UGAId|string|加速配置ID|No|
|IPList|array|源站IP列表，多个值由半角英文逗号相隔|No|
|Domain|string|源站域名|No|

## OutPublicIpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string| 线路出口EIP|No|
|Area|string|线路出口机房代号|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUPath
&ProjectId=org-xxxx
&UPathId=upath-2noe2u
```

# Response Example
```
{
    "Action": "DescribeUPathResponse", 
    "UPathSet": [
        {
            "UPathId": "upath-2noe2u", 
            "LineFromName": "\u4e2d\u56fd(\u591a\u5730)", 
            "Name": "\u4e2d\u56fd\u591a\u5730\u5230\u62c9\u5404\u65af_0", 
            "LineToName": "\u62c9\u5404\u65af", 
            "ExpireTime": 1569859200, 
            "Bandwidth": 1, 
            "OutPublicIpList": [
                {
                    "IP": "152.32.140.87", 
                    "Area": "afr-nigeria"
                }, 
                {
                    "IP": "152.32.140.102", 
                    "Area": "afr-nigeria"
                }, 
                {
                    "IP": "152.32.140.64", 
                    "Area": "afr-nigeria"
                }, 
                {
                    "IP": "152.32.140.105", 
                    "Area": "afr-nigeria"
                }, 
                {
                    "IP": "152.32.140.15", 
                    "Area": "afr-nigeria"
                }, 
                {
                    "IP": "152.32.140.55", 
                    "Area": "afr-nigeria"
                }
            ], 
            "ChargeType": "Month", 
            "UGAList": [
                {
                    "IPList": [
                        "152.32.140.170"
                    ], 
                    "Domain": "", 
                    "UGAId": "uga-2yftnppa"
                }
            ], 
            "LineId": "line_cn_afr-nigeria", 
            "CreateTime": 1542029575
        }
    ], 
    "Message": "", 
    "RetCode": 0
}
```

