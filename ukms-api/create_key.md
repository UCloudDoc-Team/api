# 创建主密钥-CreateKey

创建用户管理数据密钥的主密钥 CMK（Customer Master Key）。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Description|string|主密钥的描述信息, 长度不能超过 8192 个字符|No|
|Alias|string|别名，可为空，不能以ucloud/(不区分大小写)开头的保留别名，限制长度36字符，相同项目下别名不能重复|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Status|string|操作结果,如 success: 成功；failure: 失败|No|
|KeyId|string|CMK 的唯一标识符|No|
|Description|string|CMK 的相关描述说明|No|
|Enabled|bool|是否启用|No|
|CreatedTime|int|创建时间|No|
|LastModifiedTime|int|最后修改时间|No|
|RequestUuid|string|此次请求的唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateKey
&ProjectId=org-mjwvpk
&Description=description
&Alias=nyScYpru
```

# Response Example
```
{
    "Status": "success", 
    "KeyId": "ukms-xxxx", 
    "RetCode": 0, 
    "Enabled": true, 
    "Action": "CreateKeyResponse", 
    "CreatedTime": 1545049380, 
    "RequestUuid": "91a4229e-3c9f-4a81-85ab-68c6a14f3f99", 
    "LastModifiedTime": 1545049380, 
    "Description": "description"
}
```

