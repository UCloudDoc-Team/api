# 获取数据库中所有表-ListCatalogTables

获取用户指定的数据库中的所有表名称

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库名称|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|请求ID|No|
|TotalCount|int|数据表总数|No|
|Tables|array|该数据库中数据表的集合|No|

## Tables
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Names|string|数据表名称|**Yes**|
|Columns|array|数据表的所有列|**Yes**|

## Column
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|列名称|**Yes**|
|Type|string|列的数据类型|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ListCatalogTables
&Region=cn-bj
&Database=default
&ProjectId=oPcVYRZv
```

# Response Example
```
{
    "Action": "ListCatalogTablesResponse", 
    "TotalCount": 4, 
    "Request": "2bb5dd25-650b-4836-a7fa-0ca2e84ba2e8", 
    "RetCode": 0, 
    "Tables": [
        {
            "Name": "nation", 
            "Columns": [
                {
                    "Type": "bigint", 
                    "Name": "n_nationkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_name"
                }, 
                {
                    "Type": "bigint", 
                    "Name": "n_regionkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_comment"
                }
            ]
        }, 
        {
            "Name": "nation2", 
            "Columns": [
                {
                    "Type": "bigint", 
                    "Name": "n_nationkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_name"
                }, 
                {
                    "Type": "bigint", 
                    "Name": "n_regionkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_comment"
                }
            ]
        }, 
        {
            "Name": "nation3", 
            "Columns": [
                {
                    "Type": "bigint", 
                    "Name": "n_nationkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_name"
                }, 
                {
                    "Type": "bigint", 
                    "Name": "n_regionkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_comment"
                }
            ]
        }, 
        {
            "Name": "nation4", 
            "Columns": [
                {
                    "Type": "bigint", 
                    "Name": "n_nationkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_name"
                }, 
                {
                    "Type": "bigint", 
                    "Name": "n_regionkey"
                }, 
                {
                    "Type": "string", 
                    "Name": "n_comment"
                }
            ]
        }
    ]
}
```

