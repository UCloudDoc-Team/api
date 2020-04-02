# 网页防篡改全局开关-ModifyGlobalAssuranceState

网页防篡改全局开关

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|State|string|网页防篡改全局开关状态，on:开,off:关|**Yes**|
|Domain|string|添加域名|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyGlobalAssuranceState
&Domain=DLzVSBvT
&State=off
```

# Response Example
```
{
    "Action": "ModifyGlobalAssuranceStateResponse", 
    "RetCode": 0
}
```

