# 发送短信息-SendUSMSMessage

发送短信息。短信字数超过70个后，按照每66个进行切割(因为要加上1/3), 2/3)等字样，占用4个字长)。短信最大长度不能超过600个字。每个汉字、数字、字母、字符都按一个字计

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|PhoneNumbers.N|string|电话号码数组，电话号码格式为(60)1xxxxxxxx，()中为国际长途区号(如中国为86或0086，两种格式都支持)，后面为电话号码.若不传入国际区号，如1851623xxxx，则默认为国内手机号|**Yes**|
|TemplateParams.N|string|模板参数数组，以TempalteParams.0，TempalteParams.1.。。格式。若模板ID指定的模板无可变参数，则不传入该参数。模板参数个数与模板不匹配，则不允许发送|**Yes**|
|TemplateId|string|模板ID。若指定的模板ID审核未通过(status不等于2)则不允许发送|**Yes**|
|SigContent|string|使用的签名，如果不输入则使用默认签名，若没有申请默认签名不允许发送；若输入的签名没有申请，则无法发送|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|发生错误时表示错误描述|**Yes**|
|SessionNo|string|本次提交发送的短信的唯一ID，可根据该值查询本次发送的短信列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=SendUSMSMessage
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cCArXerm
&PhoneNumbers=gmtlHwlQ
&MessageContent=lRntklUs
&Signature=zWYCdRsB
&TemplateId=DnsuwvfS
```

# Response Example
```
{
    "Action": "SendUSMSMessageResponse", 
    "SessionNo": "qDLBzhgf", 
    "Message": "BrzxdsFR", 
    "RetCode": 0
}
```

