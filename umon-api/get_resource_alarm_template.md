# 获取资源绑定的告警模板-GetResourceAlarmTemplate

获取资源绑定的告警模板

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ResourceType|string|资源类型（与DescribeResourceMetric中一致）|**Yes**|
|ResourceId.n|string|资源id列表|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|请见ResourceTemplateBound|**Yes**|

## ResourceTemplateBound
|Parameter name|Type|Description|Required|
|---|---|---|---|
|HasAlarmTemlate|string|是否绑定了告警模板，Yes：是；No：否。若为No，不展示AlarmTemplateId、AlarmTemplateName、Remark|**Yes**|
|ResourceId|string|资源id|**Yes**|
|AlarmTemplateId|int|告警模板id|No|
|AlarmTemplateName|string|告警模板名称|No|
|IsDefault|string|是否默认模板，Yes：是；No：否|No|
|Remark|string|模板备注|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetResourceAlarmTemplate
&Region=cn-bj2
&ProjectId=org-kk3qlr
&ResourceType=uhost
&ResourceId.0=uhost-xxx
```

# Response Example
```
{
    "Action": "GetResourceAlarmTemplateResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "Remark": "默认推荐模板", 
            "uuid": "9943290f-da50-4edf-a80f-xxxxx", 
            "AlarmTemplateName": "默认云主机告警模板", 
            "AlarmTemplateId": 4, 
            "ResourceId": "uhost-mwzal2", 
            "HasAlarmTemplate": "Yes", 
            "IsDefault": "Yes"
        }
    ]
}
```

