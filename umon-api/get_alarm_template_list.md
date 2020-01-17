# 获取告警模板列表-GetAlarmTemplateList

获取告警模板列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Limit|int|返回数据长度，默认为20|No|
|Offset|int|列表起始位置偏移量，默认为0|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总数量|**Yes**|
|DataSet|array|告警模板列表|**Yes**|

## AlarmTemplate
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AlarmTemplateId|int|告警模板id|**Yes**|
|AlarmTemplateName|string|告警模板名称|**Yes**|
|ResourceType|string|资源类型|**Yes**|
|BoundResourceCount|int|绑定的资源数量|**Yes**|
|IsGlobal|int|是否是全局机房模版，0不是，1是|**Yes**|
|IsDefault|string|是否为默认模板|No|
|Remark|string|备注|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetAlarmTemplateList
&Region=DGdSoave
&ProjectId=EzXfGltN
&Limit=UjSBCcay
&Offset=tMJXiqNF
&ResourceType=YsEmOUYC
```

# Response Example
```
{
    "Action": "GetAlarmTemplateListResponse", 
    "TotalCount": 4, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Remark": "pJavCcAz", 
            "BoundResourceCount": 8, 
            "ResourceType": "UaCrdVJM", 
            "AlarmTemplateName": "THwnZpbV", 
            "AlarmTemplateId": 1, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "zhMGrkaK", 
            "BoundResourceCount": 2, 
            "ResourceType": "KPJLDerL", 
            "AlarmTemplateName": "nDCuUndt", 
            "AlarmTemplateId": 9, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "wpGNxXwu", 
            "BoundResourceCount": 4, 
            "ResourceType": "tzJzMuuz", 
            "AlarmTemplateName": "ZRHjuLLX", 
            "AlarmTemplateId": 4, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "sIHLdiXA", 
            "BoundResourceCount": 6, 
            "ResourceType": "kduqaLUb", 
            "AlarmTemplateName": "zbiIKPnV", 
            "AlarmTemplateId": 4, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "YJqRXyiC", 
            "BoundResourceCount": 8, 
            "ResourceType": "zfqEzXCT", 
            "AlarmTemplateName": "DBMweHYH", 
            "AlarmTemplateId": 6, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "DsZQaLGz", 
            "BoundResourceCount": 1, 
            "ResourceType": "rKvQzdmV", 
            "AlarmTemplateName": "zDtcJJXm", 
            "AlarmTemplateId": 6, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "bXJvUkBz", 
            "BoundResourceCount": 9, 
            "ResourceType": "JXXAlxSz", 
            "AlarmTemplateName": "PHdOzEwQ", 
            "AlarmTemplateId": 3, 
            "IsDefault": "Yes"
        }, 
        {
            "Remark": "oNaALals", 
            "BoundResourceCount": 9, 
            "ResourceType": "OFddPTcu", 
            "AlarmTemplateName": "AnQVcuMA", 
            "AlarmTemplateId": 6, 
            "IsDefault": "Yes"
        }
    ]
}
```

