# 修改短信模板-UpdateUSMSTemplate

调用接口UpdateUSMSTemplate修改未通过审核的短信模板，并重新提交审核

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|TemplateId|string|短信模板ID|**Yes**|
|Template|string|新的模板内容。模板名称和模板内容必须提供一个，否则会报错。小于等于600个字|**Yes**|
|TemplateName|string|新的模板名称。小于等于32个字，每个中文、英文、数组、符合都计为一个字|No|
|Remark|string|短信模板申请原因说明，字数不超过128，每个中文、符号、英文、数字等都计为1个字。|No|

```
修改消息模板。用于修改现有模板，提交成功后，若修改了模板内容，模板状态等会重置到初创状态；若只修改模板名称，则不会重置
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|发生错误时表示错误描述|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUSMSTemplate
&ProjectId=org-bxxxxy
&TemplateId=UTA1908XXXX8B3F
&Template=alertXXXXXXXXXXXXXXXXXXXXXXXX
&TemplateName=ucloud-alert
&Remark=XXXXXXXXXXXXXXX
&UnsubscribeInfo=sUGREgjQ
```

# Response Example
```
{
    "Action": "UpdateUSMSTemplateResponse", 
    "Message": "", 
    "RetCode": 0
}
```

