# 加密-Encrypt

用于加密最多为4KB任意数据，诸如RSA密钥，数据库密钥，或者其他敏感的客户信息。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|KeyId|string|调用CreateMasterKey生成的CMK全局唯一标识符|**Yes**|
|Plaintext|string|被加密的明文数据，该字符串必须使用base64编码|**Yes**|
|EncryptionContext|string|加密时传入的加密上下文, 长度不超过 1024 个字符|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|CiphertextBlob|string|加密后的密文|**Yes**|
|Status|string|操作结果|No|
|RequestUuid|string|此次请求唯一标识符|No|

# Request Example
```
https://api.ucloud.cn/?Action=Encrypt
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
&Plaintext=QWxsIHRoaW5ncyBpbiB0aGVpciBiZWluZyBhcmUgZ29vZCBmb3Igc29tZXRoaW5nLgo=
&EncryptionContext=/Users/Documents/workspace
```

# Response Example
```
{
    "Status": "success", 
    "Action": "EncryptResponse", 
    "RetCode": 0, 
    "RequestUuid": "023a8f36-c527-4dcd-815a-8e7f36b63202", 
    "CiphertextBlob": "GlT4DX+Aw2aJrmyPBU0cEusjvy3omP1EvRx+X+EmAHQBEx2rAmze7jCY9aaElqB062o7GsaILoDJOtBU.9cA5QefbfM7HCJDTd3FxQl6xLRMu0sT6dPQPppxsW4bh4m4Zx/aK/bm1KqSdNIw5I+OGPRI2zF6sWfiXOkA9dZNU.75WFYw5ZFIWr6p3kNd5YZA=="
}
```

