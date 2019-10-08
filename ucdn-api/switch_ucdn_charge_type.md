# 切换账号计费方式-SwitchUcdnChargeType

切换账号计费方式

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ChargeType|string|计费方式。traffic代表按流量包计费，bandwidth按带宽付费|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
http://api.ucloud.cn/?Action= SwitchUcdnChargeType
&ChargeType =bandwidth
```

# Response Example
```
{
    "Action": "SwitchUcdnChargeTypeResponse", 
    "RetCode": 0
}
```

