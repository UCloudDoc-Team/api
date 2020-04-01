# 删除CC防御规则-DeleteAntiCCRule

删除CC防御规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要删除的规则ID|**Yes**|
|Domain|string|要删除的规则所属域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteAntiCCRule
&ID=6
&Domain=xxxx
&ProjectId=dcITyCJD
```

# Response Example
```
{
    "Action": "DeleteAntiCCRuleResponse", 
    "RetCode": 0
}
```

