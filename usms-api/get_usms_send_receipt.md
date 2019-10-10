# 获取短信发送回执信息-GetUSMSSendReceipt

获取短信发送回执信息。下游服务提供商回执信息返回会有一定延时，建议发送完短信以后，5-10分钟后再调用该接口拉取回执信息。若超过12小时未返回，则请联系技术支持确认原因

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|Zone|string|可用区。参见 [可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|SessionNoSet.N|string|发送短信时返回的SessionNo集合，SessionNoSet.0,SessionNoSet.1....格式|**Yes**|

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
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=dWyXGqmC
&SessionNoSet.N=aMscszsM
```

# Response Example
```
{
    "Action": "GetUSMSSendReceiptResponse", 
    "Message": "RFsAGRhp", 
    "Data": [
        "sUoSsUay"
    ], 
    "RetCode": 0
}
```

