# 删除地域IP封堵规则-DeleteWafRegionBlockRule

删除地域IP封堵规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|string|规则ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafRegionBlockRule
&ProjectId=xPRdXbMU
&ID=yJlHIMju
```

# Response Example
```
{
    "Action": "DeleteWafRegionBlockRuleResponse", 
    "RetCode": 0
}
```

