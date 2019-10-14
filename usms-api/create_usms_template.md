# 申请短信模板-CreateUSMSTemplate

调用接口CreateUSMSTemplate申请短信模板

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Purpose|int|短信模板用途类型：1-验证码类短信模板；2-系统通知类短信模板；3-会员推广类短信模板；|**Yes**|
|TemplateName|string|短信模板名称，不超过32个字符，每个中文、符号、英文、数字等都计为1个字。|**Yes**|
|Template|string|短信模板内容，说明如下：字数不超过500，每个中文、符号、英文、数组等都计为一个字；模板中的变量填写格式：{N}，其中N为大于1的整数，有多个参数时，建议N从1开始顺次，例如：{1}、{2}等；短信模板禁止仅包括变量的情况；|**Yes**|
|Remark|string|短信模板申请原因说明，字数不超过128，每个中文、符号、英文、数字等都计为1个字。|No|

?> 您可以通过调用接口CreateUSMSTemplate或者到控制台申请短信模板，短信模板需遵守 [UCloud服务协议](https://docs.ucloud.cn/management_monitor/usms/introduction/service_level)，短信模板申请流程可参见官网 [短信模板审核规范](https://docs.ucloud.cn/management_monitor/usms/introduction/2005/2103) 说明；

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回状态码描述，如果操作成功，默认返回为空|**Yes**|
|TemplateId|string|短信模板ID（短信模板申请时的工单ID）|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUSMSTemplate
&ProjectId=org-bxxxxy
&Purpose=2
&TemplateName=ucloud-alert
&Template=alertXXXXXXXXXXXXXXXXXXXXXXXX
&Remark=XXXXXXXXXXXXXXXX
```

# Response Example
```
{
    "Action": "CreateUSMSTemplateResponse", 
    "Message": "", 
    "RetCode": 0, 
    "TemplateId": "UTA190816758B3F"
}
```

