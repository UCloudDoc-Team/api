# 添加域名白名单-AddWafDomainWhiteList

添加域名白名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要添加白名单的域名|**Yes**|
|Source|string|白名单来源；可选值:用户自定义(custom)，机器行为检测(bot)，bot-rule|**Yes**|
|CIDRS.n|string|IP、网段或者IP段，传递数组|**Yes**|
|Name|string|名称|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的域名白名单ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafDomainWhiteList
&FullDomain=sjTugGcg
&Source=rtweGOQm
&CIDRS=GkyLCvmW
&ProjectId=DDpedJoB
&Type=beHhhknh
&Name=PClbwsuS
&Remark=KuFeYuFo
```

# Response Example
```
{
    "Action": "AddWafDomainWhiteListResponse", 
    "RetCode": 0, 
    "Id": 2
}
```

