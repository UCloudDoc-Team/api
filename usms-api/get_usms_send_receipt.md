# 获取短信发送状态-GetUSMSSendReceipt

调用接口GetUSMSSendReceipt短信发送状态信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SessionNoSet.N|string|发送短信时返回的SessionNo集合，SessionNoSet.0,SessionNoSet.1....格式|**Yes**|

```
短信提交发送后，可调用接口GetUSMSSendReceipt查询及获取短信发送的状态信息；若发送后未立即拿到回执状态，建议在发送后5至10分钟内在尝试代用获取，若超过12小时仍未拿到发送状态，可联系UCloud技术支持协助
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|错误描述|**Yes**|
|Data|array|回执信息集合|**Yes**|

## ReceiptPerSession
|Parameter name|Type|Description|Required|
|---|---|---|---|
|SessionNo|string|发送短信时返回的SessionNo|**Yes**|
|ReceiptSet|array|每个手机号的短信回执信息集合|**Yes**|

## ReceiptPerPhone
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Phone|string|手机号码|**Yes**|
|CostCount|int|消耗短信条数|**Yes**|
|ReceiptResult|string|回执结果|**Yes**|
|ReceiptDesc|string|回执结果描述|**Yes**|
|ReceiptTime|int|回执返回时间|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUSMSSendReceipt
&ProjectId=org-XXXXqi
&SessionNoSet.0=497XXXX4-eXXXXc-4XXX
```

# Response Example
```
{
    "Action": "GetUSMSSendReceiptResponse", 
    "Message": "Action success", 
    "Data": [
        {
            "SessionNo": "497XXXX4-eXXXXc-4XXX", 
            "ReceiptSet": [
                {
                    "CostCount": 1, 
                    "ReceiptTime": 1554168750, 
                    "ReceiptCode": "", 
                    "Phone": "185XXX9057", 
                    "ReceiptResult": "Success", 
                    "ReceiptDesc": "Successfully delivered to target phone"
                }
            ]
        }
    ], 
    "RetCode": 0
}
```

