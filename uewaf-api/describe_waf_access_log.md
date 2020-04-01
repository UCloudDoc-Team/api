# 查询用户访问日志-DescribeWafAccessLog

查询用户访问日志，最大支持10000条记录，最大支持7天内日志查询

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|
|BeginTime|int|时间戳，默认为最近1小时|No|
|EndTime|int|时间戳，默认为最近1小时|No|
|RawQuery.n|string|查询字段，形式为 字段名:查询内容 ，模糊查询以斜杠包围内容，如 ：/test/ |No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，最大100|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|string|JSON数组|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafAccessLog
&FullDomain=ZgsZKTNr
&Begin=8
&End=YGiDZWdL
&RawQuery.n=lDFllcty
&Offset=2
&Limit=3
&ProjectId=vHboPWUZ
```

# Response Example
```
{
    "Action": "DescribeWafAccessLogResponse", 
    "Res": "rGVVDsNm", 
    "RetCode": 0
}
```

