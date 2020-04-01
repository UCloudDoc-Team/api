# 删除防篡改页面-DeleteAssurancePage

删除防篡改页面

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ID|int|要删除的防篡改记录ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteAssurancePage
&ID=3
&ProjectId=snxAmRuu
```

# Response Example
```
{
    "Action": "DeleteAssurancePageResponse", 
    "RetCode": 0
}
```

