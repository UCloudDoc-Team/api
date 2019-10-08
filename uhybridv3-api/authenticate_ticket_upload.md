# 服务单上传附件鉴权-AuthenticateTicketUpload

服务单上传附件鉴权

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FileName|string|文件名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回信息|No|
|TotalCount|int|0：返回成功；1：返回失败|No|
|DataSet|object|返回对象-授权码|No|

# Request Example
```
https://api.ucloud.cn/?Action=AuthenticateTicketUpload
&FileName=MuiHOFWJ
```

# Response Example
```
{
    "Action": "AuthenticateTicketUploadResponse", 
    "RetCode": 0
}
```

