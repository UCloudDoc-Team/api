# 修改地域IP封堵规则-ModifyWafRegionBlockRule

修改地域IP封堵规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要操作的域名|**Yes**|
|ID|int|规则ID|**Yes**|
|Name|string|规则名称|**Yes**|
|ActionType|string|匹配Action，Accept or Deny（默认）|**Yes**|
|BlockRegion|string|封堵地域编码，定义与添加的api相同|**Yes**|
|Description|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=603
&ActionType=Deny
&BlockRegion=US
&Description=美国
```

# Response Example
```
{
    "Action": "ModifyWafRegionBlockRuleResponse", 
    "RetCode": 0
}
```

