# 获取数据库列表-ListCatalogDatabases

用户获取自己账号下的所有数据库名称列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|请求ID|No|
|TotalCount|int|数据库总数|No|
|DatabaseNames|array|数据库名称列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListCatalogDatabases
&Region=cn-bj
&ProjectId=RFQCWdDK
```

# Response Example
```
{
    "Action": "ListCatalogDatabasesResponse", 
    "TotalCount": 1, 
    "Request": "44ba2fe7-34ea-4d65-9a35-5f068e9ed12b", 
    "RetCode": 0, 
    "DatabaseNames": [
        "default"
    ]
}
```

