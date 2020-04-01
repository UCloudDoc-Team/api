# 添加防篡改页面-AddAssurancePage

添加防篡改页面

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Domain|string|要添加防篡改规则的域名|**Yes**|
|URL|string|要防篡改的URL|**Yes**|
|State|string|防护状态,on:开启;off:关闭|**Yes**|
|Remark|string|备注信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的规则ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddAssurancePage
&Domain=OckEACbV
&Remark=SXXGyQyX
&URL=PfNcdtam
&State=on
&ProjectId=gLfboGti
&RecordId=3
```

# Response Example
```
{
    "Action": "AddAssurancePageResponse", 
    "RetCode": 0, 
    "Id": 1
}
```

