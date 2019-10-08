# 更新主密钥描述信息-UpdateKeyDescription

更新指定主密钥的描述信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|KeyId|string|主密钥 Key ID|**Yes**|
|Description|string|新的主密钥描述信息|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Status|string|返回状态|**Yes**|
|RequestUuid|string|此次请求唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateKeyDescription
&ProjectId=org-mjwvpk
&KeyId=ukms-xkxxse
&Description=description-new
```

# Response Example
```
{
    "Status": "success", 
    "Action": "UpdateKeyDescriptionResponse", 
    "RetCode": 0, 
    "RequestUuid": "5420218a-3a17-4bfc-b662-523c085c6668"
}
```

