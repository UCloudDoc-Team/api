# 获取waf防护域名列表-DescribeWafDomainHostInfo

获取waf防护域名列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Limit|int|每页数量限制(等效page size)|**Yes**|
|Offset|int|页面偏移(等效page number)|**Yes**|
|FullDomain|string|域名，用于查询单一域名|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|string|域名总数|No|
|DomainHostList|array|域名信息列表，参考HostStatausInfo|No|

## HostStatausInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FullDomain|string|域名|No|
|WorkMode|string|工作模式|No|
|RecordID|int|域名记录ID|No|
|CertificateID|int|证书ID|No|
|Cname|string|CNAME记录值|No|
|WorkRegions|string|部署区域|No|
|AntiCC|string|是否开启CC防护|No|
|Assurance|string|是否开启网页防篡改|No|
|CreateTime|int|创建时间戳|No|
|SrcIPInfo|array|源站IP地址信息，参考SrcIPInfo|No|
|HTTPRedirection|string|http是否重定向|No|
|HTTPStatus|string|http状态描述|No|
|HTTPException|string|http异常信息|No|
|HTTPSStatus|string|https状态|No|
|HTTPSException|string|https异常描述|No|
|UniqueIP|string|是否独享IP地址|No|
|RealIPHeader|string|真实IP头部|No|
|AttackCount|int|攻击次数|No|
|DomainStatus|array|域名状态信息，参考DomainStatus|No|
|DefenceIps|object|防御IP地址表(map)，如：{"cn-gd":["192.168.1.2","192.168.1.3"]|No|

## SrcIPInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Proto|string|协议|No|
|Ip|string|源IP地址|No|
|Ports|array|源端口|No|
|URI|string|URI|No|

## DomainStatus
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|部署区域|No|
|Scheme|string|协议|No|
|Status|string|状态信息|No|
|RawStatus|string|原始状态信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainHostInfo
&ProjectId=org-xxx
&Offset=0
&Limit=10
```

# Response Example
```
{
    "Action": "DescribeWafDomainHostInfoResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DomainHostList": [
        {
            "FullDomain": "www.test.com", 
            "UniqueIP": "NO", 
            "CertificateID": 0, 
            "RealIPHeader": "default", 
            "HttpException": "Head http://106.5.27.194:80/: EOF", 
            "RecordId": 46103, 
            "AttackCount": 0, 
            "HttpStatus": "Exception", 
            "WorkRegions": "cn-bj,cn-gd", 
            "DomainStatus": [
                {
                    "Status": "Exception", 
                    "RawStatus": "Head http://106.5.185.203:80/: EOF", 
                    "Region": "cn-gd", 
                    "Scheme": "http"
                }, 
                {
                    "Status": "Exception", 
                    "RawStatus": "Head http://106.5.27.194:80/: EOF", 
                    "Region": "cn-bj", 
                    "Scheme": "http"
                }
            ], 
            "HttpsException": "", 
            "SrcIPInfo": [
                {
                    "SrcIP": "152.32.70.130", 
                    "Port": [
                        80
                    ], 
                    "URI": "http://152.32.170.130:80", 
                    "Proto": "http"
                }
            ], 
            "HttpsStatus": "Unaccess", 
            "Cname": "ce43b831.uewaf.com", 
            "HTTPRedirection": "NO", 
            "WorkMode": "Alarm", 
            "DefenceIps": {
                "cn-bj": [
                    "106.7.27.194"
                ], 
                "cn-gd": [
                    "106.7.185.203"
                ]
            }, 
            "AntiCC": "on", 
            "CreateTime": 1584695681, 
            "Assurance": "off"
        }
    ]
}
```

