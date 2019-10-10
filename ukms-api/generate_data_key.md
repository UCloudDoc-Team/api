# 创建数据密钥-GenerateDataKey

通过指定主密钥换取自动生成的数据密钥

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|KeyId|string|用于生成数据密钥的主密钥的 KeyId|**Yes**|
|EncryptionContext|string|生成数据密钥时传入的加密上下文, 长度不超过 1024 个字符|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|CiphertextBlob|string|数据密钥的密文|**Yes**|
|Plaintext|string|数据密钥的明文, 用于加密数据|**Yes**|
|Status|string|操作结果|No|
|RequestUuid|string|此次请求的唯一标识|No|

# Request Example
```
https://api.ucloud.cn/?Action=GenerateDataKey
&ProjectId=org-mjwvpk
&KeyId=ukms-oep2f0
&EncryptionContext=/Users/Documents/workspace
```

# Response Example
```
{
    "Status": "success", 
    "RetCode": 0, 
    "Plaintext": "IEM+J8/+Nrq97o4bY8O0Vw==", 
    "CiphertextBlob": "GlT4DX+Aw2aJrmyPBU0cEusjvy3omP1EvRx+X+EmAHQBEx2rAmze7jCY9aaElqB062o7GsaILoDJOtBU.lO9rRlxNIxodlT6hepKxfZtCdL/QihwrnUk7LyXxgoA=.75WFYw5ZFIWr6p3kNd5YZA==", 
    "Action": "GenerateDataKeyResponse", 
    "RequestUuid": "ed552313-02e7-40f7-a0bb-a42f39ac053a"
}
```

