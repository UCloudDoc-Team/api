# 解绑告警模板-UnbindAlarmTemplate

解绑告警模板

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ResourceType|string|资源类型，同DescribeResourceMetric支持的类型，请参考DescribeResourceMetric中的可选资源类型|**Yes**|
|ResourceId.n|string|资源id|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UnbindAlarmTemplate
&ProjectId=org-xxx
&Region= cn-bj2
&ResourceType=uhost
&ResourceId.0=uhost-xxxxx
```

# Response Example
```
{
    "Action": "UnbindAlarmTemplateResponse", 
    "RetCode": 0
}
```

