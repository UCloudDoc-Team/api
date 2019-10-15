# 获取全球加速服务加速配置信息-DescribeUGAInstance

获取全球加速服务加速配置信息，指定实例ID返回单个实例。未指定实例ID时 指定分页参数 则按创建时间降序 返回记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|UGAId|string|加速配置实例ID，如果传了实例ID 则返回匹配实例ID的记录；如果没传则返回 ProjectId 下全部实例且符合分页要求|No|
|Limit|int|返回的最大条数，默认为100，最大值400|No|
|Offset|int|偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UGAList|array|全球加速实例信息列表|No|
|TotalCount|int|符合条件的总数|No|

## UGAAInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UGAId|string|加速配置实例ID|**Yes**|
|CName|string|加速域名，请在加速区域配置您的业务域名的CName记录值为加速域名|**Yes**|
|UGAName|string|加速配置名称|**Yes**|
|IPList|array|源站IP列表，多个值由半角英文逗号相隔|No|
|Domain|string|源站域名|No|
|Location|string|源站所在区域，加速实例在绑定线路后会自动设置该值。console页面上通过该值过滤加速实例可以绑定的upath实例。注意：缺少该值会导致在console上无法修改线路|No|
|UPathSet|array|绑定的加速线路|No|
|TaskSet|array|端口配置信息（不再维护，建议使用ForwarderSet）|No|
|L4ForwarderSet|array|UGA 4层转发器配置，记录接入或回源端口，接入或回源协议信息|No|
|L7ForwarderSet|array|UGA 7层转发器配置，记录接入或回源端口，接入或回源协议信息 如绑定证书会返回证书ID|No|
|OutPublicIpList|array|线路出口IP地址|No|

## UPathSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|UPathName|string|UPath名字|No|
|UPathId|string|UPath 实例ID|No|
|Bandwidth|int|带宽 Mbps, 1~800Mbps|No|
|LineId|string|线路ID|No|
|LineFromName|string|线路起点中文名字，加速区域|No|
|LineToName|string|线路对端中文名字，源站区域|No|
|LineFrom|string|线路起点英文代号，加速区域|No|
|LineTo|string|线路对端英文代号，源站区域|No|

## UGAATask
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，包括TCP\|UDP\|HTTPHTTP\|HTTPSHTTP\|HTTPSHTTPS。TCP和UDP代表四层转发，其余为七层转发|**Yes**|

## UGAL4Forwarder
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，包括TCP\|UDP\|HTTPHTTP\|HTTPSHTTP\|HTTPSHTTPS。TCP和UDP代表四层转发，其余为七层转发|**Yes**|
|RSPort|int|RSPort，源站监听端口|**Yes**|

## UGAL7Forwarder
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Port|int|接入端口|**Yes**|
|Protocol|string|转发协议，包括TCP\|UDP\|HTTPHTTP\|HTTPSHTTP\|HTTPSHTTPS。TCP和UDP代表四层转发，其余为七层转发|**Yes**|
|RSPort|int|RSPort，源站监听端口|**Yes**|
|SSLId|string|证书ID|No|
|SSLName|string|证书名称|No|

## OutPublicIpInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IP|string| 线路出口EIP|No|
|Area|string|线路出口机房代号|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUGAInstance
&ProjectId=org-xxxx
&UGAId=uga-5ygl0d
&Limit=10
&Offset=0
```

# Response Example
```
{
    "Action": "DescribeUGAInstanceResponse", 
    "TotalCount": 1, 
    "Message": "", 
    "RetCode": 0, 
    "UGAList": [
        {
            "UPathSet": [
                {
                    "UPathId": "upath-xcacoz", 
                    "LineFromName": "中国(多地)", 
                    "LineFrom": "cn-gd", 
                    "LineToName": "洛杉矶", 
                    "UPathName": "中美加速", 
                    "Bandwidth": 1, 
                    "LineTo": "us-ca", 
                    "LineId": "line_cn-us-ca"
                }
            ], 
            "Domain": "github.com", 
            "OutPublicIpList": [
                {
                    "IP": "107.150.101.244", 
                    "Area": "us-ca"
                }, 
                {
                    "IP": "107.150.102.54", 
                    "Area": "us-ca"
                }, 
                {
                    "IP": "107.150.102.58", 
                    "Area": "us-ca"
                }, 
                {
                    "IP": "107.150.102.63", 
                    "Area": "us-ca"
                }, 
                {
                    "IP": "107.150.102.68", 
                    "Area": "us-ca"
                }, 
                {
                    "IP": "107.150.102.88", 
                    "Area": "us-ca"
                }
            ], 
            "UGAName": "github加速", 
            "L7ForwarderSet": [], 
            "CName": "xbc287.pathx.ucloudgda.com", 
            "Location": "北美", 
            "TaskSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 443, 
                    "RSPort": 0
                }
            ], 
            "UGAId": "uga-5ygl0d", 
            "IPList": [
                ""
            ], 
            "L4ForwarderSet": [
                {
                    "Protocol": "TCP", 
                    "Port": 443, 
                    "RSPort": 443
                }
            ]
        }
    ]
}
```

