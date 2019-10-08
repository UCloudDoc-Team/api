# 删除短信模板-DeleteUSMSTemplate

调用接口DeleteUSMSTemplate删除短信模板

```
1.不支持删除正在审核中的短信模板；2.短信模板删除后不可恢复，请谨慎操作。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|No|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|TemplateIds.N|int|模板ID（也即短信模板申请时的工单ID），支持以数组的方式，举例，以TemplateIds.0、TemplateIds.1...TemplateIds.N方式传入|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回状态码描述，如果操作成功，默认返回为空|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUSMSTemplate
&ProjectId=org-bxxxxy
&TemplateIds.0=UTA1908XXXX8B3F
&TemplateIds.1=UTA1908XXXX8B3F
```

# Response Example
```
{
    "Action": "DeleteUSMSTemplateResponse", 
    "Message": "", 
    "RetCode": 0
}
```

