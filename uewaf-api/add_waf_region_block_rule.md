# 添加WAF区域IP封堵规则-AddWafRegionBlockRule

添加WAF区域IP封堵规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|
|Name|string|规则名称|**Yes**|
|BlockRegion|string|封堵地域编码，格式：国家代码:区域列表大陆区支持省级和市级细分，其他只支持国家，e.g.:CN:110000\|440300\|320000代表对北京市 深圳市 江苏省 的ip进行封堵; US表示对美国ip进行封堵|**Yes**|
|ActionType|string|匹配Action，Accept or Deny（默认），Accept暂不支持|**Yes**|
|Description|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的封堵规则ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddWafRegionBlockRule
&ProjectId=org-xxx
&FullDomain=www.test.com
&Name=test
&BlockRegion=CN
&ActionType=Deny
&Description=aaa
```

# Response Example
```
{
    "Action": "AddWafRegionBlockRuleResponse", 
    "RetCode": 0, 
    "Id": 4
}
```

