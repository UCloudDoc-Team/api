# 获取SQL查询结果下载地址-GetSQLQueryDataURL

获取SQL查询分析结果文件的下载地址

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|QueryId|string|SQL查询ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|QueryId|string|SQL查询ID|No|
|QueryDataURL|string|SQL查询结果下载URL地址|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSQLQueryDataURL
&Region=cn-bj
&QueryId=20180917_025826_00001_ysv9q
&ProjectId=xzpnAimt
```

# Response Example
```
{
    "Action": "GetSQLQueryDataURLResponse", 
    "QueryId": "hbPEDPmg", 
    "QueryDataURL": "tJNWiiZa", 
    "Request": "VSwhYxHa", 
    "RetCode": 0
}
```

