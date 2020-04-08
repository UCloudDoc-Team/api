# WAF攻击源IP数概览-StatWafAttackSrcTrend

WAF攻击源IP数概览

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
|Count|int|攻击次数|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=StatWafAttackSrcTrend
&ProjectId=org-xxx
&BeginTime=1586237414
&EndTime=1586241014
```

# Response Example
```
{
    "Action": "StatWafAttackSrcTrendResponse", 
    "RetCode": 0, 
    "Result": {
        "Count": 3, 
        "Type": "AttackSrcIP", 
        "Detail": [
            {
                "Count": 1, 
                "Timestamp": 1586240820
            }, 
            {
                "Count": 1, 
                "Timestamp": 1586240880
            }, 
            {
                "Count": 1, 
                "Timestamp": 1586240940
            }
        ]
    }
}
```

