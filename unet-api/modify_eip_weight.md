# 修改弹性IP出口权重-ModifyEIPWeight

修改弹性IP的外网出口权重

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|EIPId|string|弹性IP的资源ID|**Yes**|
|Weight|int|外网出口权重, 范围[0-100] 取值为0时, 该弹性IP不会被使用. 取值为100时, 同主机下只会使用这个弹性IP，其他弹性IP不会被使用 请勿将多个绑定在同一资源的弹性IP设置为相同权重|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyEIPWeight
&Region=cn-bj2
&EIPId=eip-dr1e2n
&Weight=4
```

# Response Example
```
{
    "Action": "ModifyEIPWeightResponse", 
    "RetCode": 0
}
```

