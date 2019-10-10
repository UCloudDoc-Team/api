# 绑定告警模板-BindAlarmTemplate

绑定告警模板

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|Zone|string|可用区，如下资源类型不需要：'eip', 'sharebandwidth', 'ulb', 'ulb-vserver', 'ulb-server', 'vserver', 'ugc', 'upath'，'ugaa'|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AlarmTemplateId|string|告警模板id，调用GetAlarmTemplateList获取|**Yes**|
|ResourceType|string|资源类型，同DescribeResourceMetric支持的类型，请参考DescribeResourceMetric中的可选资源类型|**Yes**|
|ResourceId.n|string|短资源id列表|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=BindAlarmTemplate
&ProjectId=org-xxx
&Zone=cn-bj2-02
&Region= cn-bj2
&AlarmTemplateId=xxxx
&ResourceType=uhost
&ResourceId.0=uhost-xxxxx
```

# Response Example
```
{
    "Action": "BindAlarmTemplateResponse", 
    "RetCode": 0
}
```

