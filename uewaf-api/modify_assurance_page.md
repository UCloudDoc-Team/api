# 编辑防篡改页面-ModifyAssurancePage

编辑防篡改页面

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|ProjectId|int|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要编辑的防篡改记录ID|**Yes**|
|URL|string|防篡改的url|**Yes**|
|Remark|string|防篡改业务名称|**Yes**|
|State|string|是否开启防护|**Yes**|
|Domain|string|要添加防篡改规则的域名|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyAssurancePage
&ProjectId=org-xxx
&Domain=www.test.com
&ID=5
&URL=http://www.test.com/inedx.html
&State=on
&Remark=test
```

# Response Example
```
{
    "Action": "ModifyAssurancePageResponse", 
    "RetCode": 0
}
```

