# 修改防护规则优先级-ModifyWafProtectionPriorityInfo

修改防护规则优先级

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要操作的域名|**Yes**|
|RuleSetID|string|规则ID|**Yes**|
|UpDown|string|提高或者降低nice值，UP:优先级向上调整,DOWN:优先级向下调整|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafProtectionPriorityInfo
&ProjectId=bpjYsStG
&RuleSetID=siODHJTy
&UpDown=UP
&FullDomain=inVUTKhl
```

# Response Example
```
{
    "Action": "ModifyWafProtectionPriorityInfoResponse", 
    "RetCode": 0
}
```

