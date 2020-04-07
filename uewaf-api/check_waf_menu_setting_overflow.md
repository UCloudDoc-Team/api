# 校验域名和规则数是否超出指定套餐的限制-CheckWafMenuSettingOverflow

校验域名和规则数是否超出指定套餐的限制

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|不填为默认项目|No|
|EditionType|string|版本类型名，Enhanced:增强版,Deluxe:高级版,Enterprise:企业版,Professional:旗舰版（已废弃）|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UsageInfo|object|用量描述，参考UsageInfo|No|

## UsageInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IPUsage|object|独享ip用量，参考UsageInfoDetail|No|
|DomainUsage|object|已添加域名数量，参考UsageInfoDetail|No|
|BoardWidthUsageInner|object|内部带宽占用，参考UsageInfoDetail|No|
|BoardWidthUsageOuter|object|外部带宽占用，参考UsageInfoDetail|No|
|DomainLimit|object|域名数量限额，参考UsageInfoDetail|No|
|ExclusiveIPLimit|object|独享ip限额，参考UsageInfoDetail|No|
|BandwidthInner|object|内部带宽限额，参考UsageInfoDetail|No|
|BandwidthOuter|object|外部带宽限额，参考UsageInfoDetail|No|

## UsageInfoDetail
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Quota|int|配额数量|No|
|Used|int|已使用数量|No|

# Request Example
```
https://api.ucloud.cn/?Action=CheckWafMenuSettingOverflow
&ProjectId=org-xxx
```

# Response Example
```
{
    "Action": "CheckWafMenuSettingOverflowResponse", 
    "UsageInfo": {
        "customize_rule_set": {
            "Used": 0, 
            "Quota": 30
        }, 
        "BandwidthInner": {
            "Used": 0, 
            "Quota": 120
        }, 
        "user_domain_cc_rules": {
            "Used": 0, 
            "Quota": 10
        }, 
        "BandwidthOuter": {
            "Used": 0, 
            "Quota": 40
        }, 
        "ExclusiveIPLimit": {
            "Used": 0, 
            "Quota": 8
        }, 
        "DomainLimit": {
            "Used": 3, 
            "Quota": 20
        }
    }, 
    "RetCode": 0
}
```

