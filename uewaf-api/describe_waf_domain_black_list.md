# 获取域名黑名单列表-DescribeWafDomainBlackList

获取域名黑名单列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要查询的域名|**Yes**|
|Limit|int|每页数量限制(等效page size)|**Yes**|
|Offset|int|页面偏移(等效page number)|**Yes**|
|Filter|string|想要查找的IP、网段或者IP段，传递数组（CIDRS）|No|
|Sort|string|排序参数，支持"ExpireTime", "-ExpireTime", "CreateTime", "-CreateTime"|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|object|黑名单返回结果，参考BWInfoRes|No|

## BWInfoRes
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Total|int|总数|No|
|Count|int|返回数量|No|
|Info|array|详情列表，参考BWInfo|No|

## BWInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ID|int|黑名单/白名单规则ID|No|
|Type|string|类型|No|
|Source|string|加入方式(黑)|No|
|CIDRS|array|IP列表|No|
|CreateTime|string|加入时间|No|
|ExpireTime|int|过期时间|No|
|State|int|状态|No|
|SRC|string|加入方式(白)|No|
|Geo|array|位置信息|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
&Offset=0
&Limit=10
&Remark=test
```

# Response Example
```
{
    "Action": "DescribeWafDomainBlackListResponse", 
    "Res": {
        "Count": 3, 
        "Info": [
            {
                "SRC": "", 
                "Remark": "", 
                "Name": "", 
                "CIDRS": [
                    "1.2.3.4"
                ], 
                "ID": 251276, 
                "ExpireTime": 1585193463, 
                "Source": "custom", 
                "State": 0, 
                "ActionType": "forbidden", 
                "Type": "custom", 
                "CreateTime": "2020-03-26 11:21:03"
            }, 
            {
                "SRC": "", 
                "Remark": "", 
                "Name": "", 
                "CIDRS": [
                    "2.2.2.2-2.2.2.10"
                ], 
                "ID": 252062, 
                "ExpireTime": 1585332545, 
                "Source": "custom", 
                "State": 0, 
                "ActionType": "forbidden", 
                "Type": "custom", 
                "CreateTime": "2020-03-28 01:59:05"
            }, 
            {
                "SRC": "", 
                "Remark": "", 
                "Name": "", 
                "CIDRS": [
                    "2.2.2.2"
                ], 
                "ID": 252731, 
                "ExpireTime": 1585880019, 
                "Source": "custom", 
                "State": 0, 
                "ActionType": "forbidden", 
                "Type": "custom", 
                "CreateTime": "2020-04-03 10:03:39"
            }
        ], 
        "Total": 3
    }, 
    "RetCode": 0
}
```

