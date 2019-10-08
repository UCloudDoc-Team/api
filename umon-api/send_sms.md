# 发送短信-SendSms

发送短信

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Phone.n|string|接收短信的手机号码|**Yes**|
|Content|string|短信内容（每超过70个字会多拆分一条短信）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=SendSms
&Phone.n=meJFydES
&Content=ANHcDrXp
```

# Response Example
```
{
    "Action": "SendSmsResponse", 
    "RetCode": 0
}
```

