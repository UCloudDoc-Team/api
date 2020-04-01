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
|UsageInfo|object|用量描述|No|

## UsageInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|IPUsage|int|独享ip用量|No|
|DomainUsage|int|已添加域名数量|No|
|BoardWidthUsageInner|int|内部带宽占用|No|
|BoardWidthUsageOuter|int|外部带宽占用|No|
|DomainLimit|int|域名数量限额|No|
|ExclusiveIPLimit|int|独享ip限额|No|
|BandwidthInner|int|内部带宽限额|No|
|BandwidthOuter|int|外部带宽限额|No|

# Request Example
```
https://api.ucloud.cn/?Action=CheckWafMenuSettingOverflow
&EditionType=Enterprise
&ProjectId=qIHzvtJw
```

# Response Example
```
{
    "Action": "CheckWafMenuSettingOverflowResponse", 
    "UsageInfo": "LasEMLGk", 
    "RetCode": 0
}
```

