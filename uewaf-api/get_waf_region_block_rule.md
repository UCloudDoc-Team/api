# 查询区域IP封堵规则-GetWafRegionBlockRule

查询区域IP封堵记录

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|查询域名 |**Yes**|
|Offset|int|分页查询偏移设置|No|
|Limit|int|单页数量限制|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Count|int|规则数量|No|
|RuleList|object|规则列表，参考RegionBlackInfo|No|

## RegionBlackInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Name|string|规则名称|No|
|FullDomain|string|所属域名|No|
|Action|string|执行动作|No|
|Regions|string|生效区域|No|
|Description|string|规则描述|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetWafRegionBlockRule
&ProjectId=VwbtdkcY
&FullDomain=tMivwGKu
&Offset=8
&Limit=7
```

# Response Example
```
{
    "Action": "GetWafRegionBlockRuleResponse", 
    "Count": 6, 
    "RetCode": 0, 
    "RuleList": {}
}
```

