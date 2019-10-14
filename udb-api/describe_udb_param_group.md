# 获取参数信息-DescribeUDBParamGroup

获取参数组详细参数信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|GroupId|int|参数组id，如果指定则获取描述，否则是列表操作，需要 指定Offset/Limit|No|
|Offset|int|分页显示的起始偏移，列表操作则指定|No|
|Limit|int|分页显示的条目数，列表操作则指定|No|
|IsInUDBC|bool|是否选取专区中配置|No|
|RegionFlag|bool|是否是跨可用区的配置文件|No|
|ClassType|string|如果未指定GroupId，则可选是否选取特定DB类型的配置(sql, nosql, postgresql, sqlserver)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|参数组列表 参照UDBParamGroupSet|No|
|TotalCount|int|参数组总数，列表操作时才会有该参数|No|

## UDBParamGroupSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GroupId|int|参数组id|No|
|GroupName|string|参数组名称|No|
|DBTypeId|string|DB类型id，mysql/mongodb按版本细分各有一个id 目前id的取值范围为[1,7],数值对应的版本如下 1：mysql-5.5，2：mysql-5.1，3：percona-5.5 4：mongodb-2.4，5：mongodb-2.6，6：mysql-5.6 7：percona-5.6|No|
|Description|string|参数组描述|No|
|Modifiable|bool|参数组是否可修改|No|
|ParamMember|array|参数的键值对表 UDBParamMemberSet|No|

## UDBParamMemberSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Key|string|参数名称|No|
|Value|string|参数值|No|
|ValueType|int|参数值应用类型，取值范围为{0,10,20,30},各值 代表意义为 0-unknown、10-int、20-string、 30-bool|No|
|AllowedVal|string|允许的值(根据参数类型，用分隔符表示)|No|
|ApplyType|int|参数值应用类型,取值范围为{0,10,20}，各值代表 意义为0-unknown、10-static、20-dynamic|No|
|Modifiable|bool|是否可更改，默认为false|No|
|FormatType|int|允许值的格式类型，取值范围为{0,10,20}，意义分 别为PVFT_UNKOWN=0,PVFT_RANGE=10, PVFT_ENUM=20|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDBParamGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&GroupId=20                               
```

# Response Example
```
{
    "Action": "DescribeUDBParamGroupResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "DataSet": [
        {
            "DBTypeId": "mongodb-2.4", 
            "Modifiable": true, 
            "ParamMember": [
                {
                    "FormatType": "PVFT_ENUM", 
                    "ValueType": "PVT_BOOL", 
                    "Modifiable": true, 
                    "Value": "false", 
                    "Key": "auth", 
                    "ApplyType": "PAT_STATIC", 
                    "AllowedVal": "true,false"
                }, 
                {
                    "FormatType": "PVFT_RANGE", 
                    "ValueType": "PVT_INT", 
                    "Modifiable": true, 
                    "Value": "2000", 
                    "Key": "maxConns", 
                    "ApplyType": "PAT_STATIC", 
                    "AllowedVal": "1-100000"
                }
            ], 
            "GroupName": "mongodb2.4默认配置", 
            "GroupId": 20, 
            "Description": "mongodb2.4默认配置"
        }
    ]
}
```

