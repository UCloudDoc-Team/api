# 启用主密钥-EnableKey

启用主密钥

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|KeyId|string|需要查看的主密钥对应的 KeyId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Status|string| 操作结果|**Yes**|
|RequestUuid|string|此次请求唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=EnableKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
```

# Response Example
```
{
    "Status": "success", 
    "Action": "EnableKeyResponse", 
    "RetCode": 0, 
    "RequestUuid": "91be1535-89f5-439d-b7f5-e8ee7c8f2627"
}
```

