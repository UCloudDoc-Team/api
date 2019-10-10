# 获取云数据库支持类型-DescribeUDBType

获取UDB支持的类型信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|DB类型列表 参数见 UDBTypeSet|No|

## UDBTypeSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DBTypeId|string|DB类型id，mysql/mongodb按版本细分各有一个id, 目前id的取值范围为[1,7],数值对应的版本如下： 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6， 7：percona-5.6|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBType
&Region=cn-bj2
&Zone=cn-bj2-04
```

# Response Example
```
{
    "Action": "DescribeUDBTypeResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "DBTypeId": "mysql-5.1"
        }, 
        {
            "DBTypeId": "mysql-5.5"
        }, 
        {
            "DBTypeId": "percona-5.5"
        }, 
        {
            "DBTypeId": "mongodb-2.4"
        }
    ]
}
```

