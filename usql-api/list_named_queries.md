# 获取命名查询列表-ListNamedQueries

获取用户保存的SQL查询列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|Limit|int|返回的SQL查询记录上限，默认值为20|No|
|Offset|int|SQL查询记录开始位置，默认值为0|No|
|Type|string|【非公开】SQL查询类型， 默认为空时，则用户私有的SQL查询， example时，则为示例SQL|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|TotalCount|int|保存的SQL查询总数|No|
|NamedQueries|array|保存的SQL查询集合|No|

## NamedQuery
|Parameter name|Type|Description|Required|
|---|---|---|---|
|NamedQueryId|int|已保存查询ID|**Yes**|
|QueryName|string|查询名称|No|
|QueryDescription|string|查询描述|No|
|QueryString|string|查询SQL语句|No|
|CreateTime|int|查询创建时间|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListNamedQueries
&Region=cn-xxxx
&ProjectId=org-33511
&Limit=20
&Offset=0

```

# Response Example
```
{
    "Action": "ListNamedQueriesResponse", 
    "TotalCount": 1, 
    "Request": "2a7a6712-f837-4cb9-a33c-b81f37917ef3", 
    "RetCode": 0, 
    "NamedQueries": [
        {
            "QueryName": "named_sql", 
            "QueryDescription": "yyyyyyyyyy", 
            "QueryId": 1, 
            "QueryString": "SELECT * FROM xxxxxx;", 
            "CreateTime": "2018-08-14T12:55:54.000+0000"
        }
    ]
}
```

