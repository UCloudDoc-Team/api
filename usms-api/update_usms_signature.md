# 修改短信签名-UpdateUSMSSignature

调用接口UpdateUSMSSignature修改未通过审核的短信签名，并重新提交审核

```
申请短信签名后，如果未通过审核，则可通过调用接口UpdateUSMSSignature修改未通过审核的短信签名，并重新提交审核；
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SigId|string|签名ID（也即短信签名申请时的工单ID），支持以数组的方式，举例，以SigIds.0、SigIds.1...SigIds.N方式传入   |**Yes**|
|SigContent|string|新的短信签名名称；长度为2-12个字符, 可包含中文、数字和符号；无需填写【】或[]，系统会自动添加|**Yes**|
|SigType|int|签名类型，说明如下：0-公司或企业的全称或简称；1-App应用的全称或简称；2-工信部备案网站的全称或简称；3-公众号或小程序的全称或简称；4-商标名的全称或简称；5-政府/机关事业单位/其他单位的全称或简称；|**Yes**|
|SigPurpose|int|签名用途，0-自用，1-他用；|**Yes**|
|File|string|短信签名的资质证明文件，需先进行base64编码格式转换，此处填写转换后的字符串。文件大小不超过4 MB|**Yes**|
|CertificateType|int|签名的资质证明文件类型，需与签名类型保持一致，说明如下：0-三证合一/企业营业执照/组织机构代码证书/社会信用代码证书；1-应用商店后台开发者管理截图；2-备案服务商的备案成功截图(含域名，网站名称，备案号)；3-公众号或小程序的管理界面截图；4-商标注册证书；5-组织机构代码证书、社会信用代码证书；|No|
|ProxyFile|string|短信签名授权委托文件，需先进行base64编码格式转换，此处填写转换后的字符串。文件大小不超过4 MB；当您是代理并使用第三方的签名时（也即SigPurpose为1-他用），该项为必填项；|No|

```
短信签名需符合[UCloud服务协议](https://docs.ucloud.cn/management_monitor/usms/introduction/service_level)，短信签名申请流程可参见官网[短信签名审核规范](https://docs.ucloud.cn/management_monitor/usms/introduction/2005/2103)说明；
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回状态码描述，如果操作成功，默认返回为空|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUSMSSignature
&ProjectId=org-bxxxxy
&SigId=SIG20190XXX2C1844
&SigType=0
&SigContent=UCloud
&SigPurpose=0
&CertificateType=0
&File=iVBORw0KGgoXXXXXXXXXXXXXXXXXXNSUhEU
```

# Response Example
```
{
    "Action": "UpdateUSMSSignatureResponse", 
    "Message": "", 
    "RetCode": 0
}
```

