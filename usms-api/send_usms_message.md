# 发送短信-SendUSMSMessage

调用接口SendUSMSMessage发送短信

```
在一次请求中，最多可以向1000个手机号码发送相同内容的短信；
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|PhoneNumbers.N|string|电话号码数组，电话号码格式为(60)1xxxxxxxx，()中为国际长途区号(如中国为86或0086，两种格式都支持)，后面为电话号码.若不传入国际区号，如1851623xxxx，则默认为国内手机号|**Yes**|
|SigContent|string|短信签名名称，请到[USMS控制台](https://console.ucloud.cn/usms)的签名管理页面查看；使用的短信签名必须是已申请并且通过审核；|**Yes**|
|TemplateId|string|模板ID（也即短信模板申请时的工单ID），请到[USMS控制台](https://console.ucloud.cn/usms)的模板管理页面查看；使用的短信模板必须是已申请并通过审核；|**Yes**|
|TemplateParams.N|string|模板参数数组，以TempalteParams.0，TempalteParams.1.。。格式。若模板ID指定的模板无可变参数，则不传入该参数。模板参数个数与模板不匹配，则限制发送|**Yes**|
|ExtendCode|string|短信扩展码，格式为阿拉伯数字串，默认不开通，如需开通请联系 UCloud技术支持|No|

```
支持在一次请求中向多个不同的手机号码发送相同内容的短信；超过70个字数将按照“每70个字数作为1条短信计费”（超过70个字提交至运营商时会在内容前置打上“1/2)”、“1/2)”，会占用4个字符），单次发送的短信字数上限为600个；字母、汉字、中英文标点符号，均按照1个字数计算；
```

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
&ProjectId=org-XXXXqi
&PhoneNumbers.0=185XXXX9057
&TemplateParams.0=123456
&SigContent=UCloud
&TemplateId=UTA19XXXX2D5BEC
&PublicKey=vsRhB0Qzo9elXXXXXkw8o/vmss8Tb0vxi74A=
```

# Response Example
```
{
    "Action": "SendUSMSMessageResponse", 
    "SessionNo": "5a3XXXXXXb-7XXXX2-4XXX", 
    "Message": "提交发送成功", 
    "RetCode": 0
}
```

