# 获取UDBbinlog列表-DescribeUDBInstanceBinlog

获取UDB指定时间段的binlog列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DBId|string|DB实例Id|**Yes**|
|BeginTime|int|过滤条件:起始时间(时间戳)|**Yes**|
|EndTime|int|过滤条件:结束时间(时间戳)|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|获取的Binlog信息列表 UDBInstanceBinlogSet|No|

## UDBInstanceBinlogSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|Binlog文件名|No|
|Size|int|Binlog文件大小|No|
|BeginTime|int|Binlog文件生成时间(时间戳)|No|
|EndTime|int|Binlog文件结束时间(时间戳)|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBInstanceBinlog
&Region=cn-bj2
&DBId=2bbf9968-2ded-48c5-89c0-4f4d683bdd6c
&BeginTime=1432569600
&EndTime=1432588600
```

# Response Example
```
{
    "Action": "DescribeUDBInstanceBinlogResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "EndTime": 1432698250, 
            "BeginTime": 1432698250, 
            "Name": "mysql-bin.000004", 
            "Size": 67543
        }, 
        {
            "EndTime": 1432699250, 
            "BeginTime": 1432699250, 
            "Name": "mysql-bin.000005", 
            "Size": 67292
        }
    ]
}
```

