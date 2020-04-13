# 删除信息安全过滤规则-DeleteWafResponseFilter

删除信息安全过滤规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|要操作的域名|**Yes**|
|ID|string|要删除的规则ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteWafResponseFilter
&ProjectId=org-xxx
&FullDomain=www.test.com
&ID=1155
```

# Response Example
```
{
    "Action": "DeleteWafResponseFilterResponse", 
    "RetCode": 0
}
```

