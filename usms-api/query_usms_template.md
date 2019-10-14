# 查询短信模板申请状态-QueryUSMSTemplate

调用接口QueryUSMSTemplate查询短信模板申请状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|TemplateId|string|模板ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|当RetCode不为0时，Message中显示具体错误描述|No|
|Data|object|短信模板明细信息|No|

## OutTemplate
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TemplateId|string|短信模板ID|**Yes**|
|Purpose|int|模板类型，选项：1-验证码类 2-通知类 3-会员推广类|**Yes**|
|TemplateName|string|短信模板名称|**Yes**|
|Template|string|短信模板内容|**Yes**|
|UnsubscribeInfo|string|退订信息；一般填写方式“回T退订”，当purpose为3（也即会员推广类）时，为必填项|**Yes**|
|Status|int|短信模板状态；状态说明：0-待审核，1-审核中，2-审核通过，3-审核未通过，4-被禁用|**Yes**|
|Remark|string|模板说明|**Yes**|
|ErrDesc|string|审核失败原因|**Yes**|
|CreateTime|int|创建时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryUSMSTemplate
&ProjectId=pro-xxxxx
&TemplateId=UTA190715D9108C
```

# Response Example
```
{
    "Action": "QueryUSMSTemplateResponse", 
    "Message": "", 
    "Data": {
        "Status": 2, 
        "TemplateName": "验证码模板01", 
        "Template": "您的验证码为{1}，请在{2}分钟内使用，勿透露给他人。", 
        "TemplateId": "UTA190715D9108C", 
        "ErrDesc": "", 
        "CreateTime": 1566783067
    }, 
    "RetCode": 0
}
```

