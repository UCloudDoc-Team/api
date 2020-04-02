# UEWAF攻击源IP数概览-StatWafAttackSrcTrend

UEWAF攻击源IP数概览

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填表示默认项目|No|
|BeginTime|int|起始时间，时间戳，单位：秒|**Yes**|
|EndTime|int|终止时间，时间戳，单位：秒|**Yes**|
|Domain|string|要统计的域名|No|
|Extent|int|统计区间，单位：秒，取值范围0-7200|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Result|object|攻击详情，参考StatAttackSrcResult|No|

## StatAttackSrcResult
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Count|int|返回节点个数|**Yes**|
|Detail|array|攻击源详情数组，参考StatAttackSrcDetail|**Yes**|

## StatAttackSrcDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Timestamp|int|时间戳|**Yes**|
|Count|string|攻击次数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafAttackSrcTrend
&ProjectId=JQKhlExt
&Domain=cNWtjyJa
&BeginTime=6
&EndTime=8
&Extent=7
```

# Response Example
```
{
    "Action": "StatWafAttackSrcTrendResponse", 
    "RetCode": 0, 
    "Detail": [
        {
            "Count": "TekTOFjF", 
            "Timestamp": 8
        }
    ]
}
```

