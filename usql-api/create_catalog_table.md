# 创建表-CreateCatalogTable

在数据目录中的指定数据库下创建新的数据表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID，不填则为默认项目|No|
|DatabaseName|string|数据库的名称|**Yes**|
|TableName|string|数据表的名称|**Yes**|
|Location|string|数据存储位置|**Yes**|
|Column.N.Name|string|第N个字段的名称，例如：第一个字段的名称：Column.0.Name|**Yes**|
|Column.N.Type|string|第N个字段的类型，例如：第一个字段的类型：Column.0.Type|**Yes**|
|Formation|string|数据格式：比如CSV，ORC， TSV等|**Yes**|
|Property.N.Key|string|第N个表属性的值，例如：第一个表属性的名称：Property.0.Key|No|
|Property.N.Value|string|第N个表属性的值，例如：第一个表属性的值：Property.0.Value|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求的ID|No|
|DatabaseName|string|新数据表所属数据库名称|No|
|TableName|string|新数据表的名称|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateCatalogTable
&Region=cn-zj
&ProjectId=JQswhxDD
&DatabaseName=db_a
&TableName=nation
&Location=ufile://usql/tpc/tpch-s1/nation
&Formation=CSV
&Column.0.Name=n_nationkey
&Column.0.Type=bigint
&Column.1.Name=n_name
&Column.1.Type=string
&Column.2.Name=n_regionkey
&Column.2.Type=bigint
&Column.3.Name=n_comment
&Column.3.Type=string
&Property.0.Key=delimiter
&Property.0.Value=,
&Property.1.Name=classification
&Property.1.Type=csv
&Property.2.Name=skip.header.line.count
&Property.2.Type=1
```

# Response Example
```
{
    "Action": "CreateCatalogTableResponse", 
    "TableName": "nation", 
    "Request": "1c5acb36-e5b4-46af-b9b1-52455cd53175", 
    "RetCode": 0, 
    "DatabaseName": "db_a"
}
```

