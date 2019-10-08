# 查询短信签名申请状态-QueryUSMSSignature

调用接口QueryUSMSSignature查询短信签名申请状态

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|SigId|string|已申请的短信签名ID（短信签名申请时的工单ID）；签名ID和签名至少需填写1项；|No|
|SigContent|string|签名内容；签名ID和签名至少需填写1项；|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|发生错误时，表示具体错误描述|**Yes**|
|Data|object|签名信息|**Yes**|

## OutSignature
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SigId|string|签名ID|**Yes**|
|SigContent|string|签名内容|**Yes**|
|Status|int|签名状态。0-待审核 1-审核中 2-审核通过 3-审核未通过 4-被禁用 |**Yes**|
|ErrDesc|string|签名审核失败原因|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryUSMSSignature
&ProjectId=BLAfnnPS
&SigId=SIG20190711D48C1F
```

# Response Example
```
{
    "Action": "QueryUSMSSignatureResponse", 
    "Message": "", 
    "Data": {
        "Status": 2, 
        "ErrDesc": "", 
        "SigContent": "test", 
        "SigId": "SIG20190711D48C1F"
    }, 
    "RetCode": 0
}
```

