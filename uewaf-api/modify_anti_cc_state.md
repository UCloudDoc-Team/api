# 更改域名CC防御状态-ModifyAntiCCState

更改域名CC防御状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|添加防护规则的域名|**Yes**|
|State|string|CC防护功能开关，on:开启;off：关闭|**Yes**|
|Mode|string|CC防护模式，normal:正常;,urgent:紧急;|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyAntiCCState
&ProjectId=DsrDCjOH
&Domain=xxx
&State=xxx
&Mode=xxx
```

# Response Example
```
{
    "Action": "ModifyAntiCCStateResponse", 
    "RetCode": 0
}
```

