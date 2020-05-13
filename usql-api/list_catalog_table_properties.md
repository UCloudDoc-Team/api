# 获取数据表的参数列表-ListCatalogTableProperties

获取用户指定名称的数据表的所有参数

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|
|TableName|string|数据表名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DatabaseName|string|数据库名称|No|
|TableName|string|数据表名称|No|
|TableProperties|array|数据表属性列表|No|

## TableProperty
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Value|string|属性值|No|
|Name|string|属性名|No|

# Request Example
```
https://api.ucloud.cn/?Action=ListCatalogTableProperties
&Region=cn-xxx
&ProjectId=ilbjABtv
&DatabaseName=default
&TableName=tbl3


```

# Response Example
```
{
    "RetCode": 0, 
    "Request": "81b7b1b3-2a61-4d68-8124-622a982c5c3f", 
    "TableName": "tbl3", 
    "DatabaseName": "default", 
    "Action": "ListCatalogTablePropertiesResponse", 
    "TableProperties": [
        {
            "Name": "skip.header.line.count", 
            "Value": "1"
        }, 
        {
            "Name": "totalSize", 
            "Value": "0"
        }, 
        {
            "Name": "delimiter", 
            "Value": "|"
        }, 
        {
            "Name": "numFiles", 
            "Value": "0"
        }, 
        {
            "Name": "transient_lastDdlTime", 
            "Value": "1534822799"
        }, 
        {
            "Name": "classification", 
            "Value": "csv"
        }
    ]
}
```

