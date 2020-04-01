# 获取域名白名单列表-DescribeWafDomainWhiteList

获取域名白名单列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要获取的白名单的域名|**Yes**|
|Limit|int|每个请求限制返回数量，等效于page size|**Yes**|
|Offset|int|偏移，等效于 page number|**Yes**|
|Filter|string|想要查找的IP、网段或者IP段，传递数组（CIDRS）|No|
|Sort|string|排序参数，支持"CreateTime", "-CreateTime"|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|object|白名单返回结果，参考BWInfoRes|**Yes**|

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
|Src|string|加入方式(白)|No|
|Geo|array|位置信息|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafDomainWhiteList
&ProjectId=aECDuZYI
&Sort=tboluBRT
&Name=nmtzenuI
&RecordId=7
&Remark=TPxMuyri
```

# Response Example
```
{
    "Action": "DescribeWafDomainWhiteListResponse", 
    "RetCode": 0
}
```

