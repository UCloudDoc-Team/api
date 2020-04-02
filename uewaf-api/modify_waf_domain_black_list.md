# 编辑域名黑名单-ModifyWafDomainBlackList

编辑域名黑名单

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|黑名单记录ID|**Yes**|
|Type|string|类型：境内(internal)、境外(oversea)，自定义(custom)|**Yes**|
|ActionType|string|动作: captcha/forbidden|**Yes**|
|ExpireTime|int|过期时间,即有效时长，单位为秒,永不过期传0|**Yes**|
|FullDomain|string|该条记录所属的域名|**Yes**|
|CIDRS.n|string|IP、网段或者IP段，传递数组；类型为custom时必填|No|
|Name|string|规则名称|No|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyWafDomainBlackList
&ProjectId=fpcnfSrk
FullDomain=xxxx
&ID=5
&Type=YOnEqBOa
ActionType=xxxx
&CIDRS.0=SlQLdDPP
&ExpireTime=2
&Name=xwYgaYas
&Remark=XEAffKZy
```

# Response Example
```
{
    "Action": "ModifyWafDomainBlackListResponse", 
    "RetCode": 0
}
```

