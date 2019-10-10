# 解密-Decrypt

用于解密密文数据，得到明文数据。（该密文数据必须是通过 GenerateDataKey 或 Encrypt 接口生成的。）

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|CiphertextBlob|string|由 GenerateDataKey 或 Encrypt 生成的加密后的数据密钥|**Yes**|
|EncryptionContext|string|解密时传入的加密上下文，内容必须与请求 GenerateDataKey 或者 Encrypt 时填入的上下文一致，长度不超过 1024 个字符|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|KeyId|string|加密该数据密钥的主密钥的 KeyId|**Yes**|
|Plaintext|string|解密后数据密钥的明文|**Yes**|
|Status|string|操作结果|No|

# Request Example
```
https://api.ucloud.cn/?Action=Decrypt
&ProjectId=org-mjwvpk
&CiphertextBlob=be0sNdakG9SmQu+dJc1mQgMMWPubCI3Wjp8S6/kg6PksBKrcV18j/uPtCRKjDeRhviBRs33yKmudXel6.KiQ4h/5NIk3mYj7//c5DmgUr8juQ2WwajYfZ7GJYU8vjk4N+32Em+dpn2VoOVAvFDjovmLUUn7wpXd4Z13mA35Cm.LxUAY5umOfawSgIKbMZtLQ==
&EncryptionContext=/Users/Documents/workspace
```

# Response Example
```
{
    "Status": "success", 
    "KeyId": "ukms-xkxxse", 
    "RetCode": 0, 
    "Plaintext": "QWxsIHRoaW5ncyBpbiB0aGVpciBiZWluZyBhcmUgZ29vZCBmb3Igc29tZXRoaW5nLgo=", 
    "Action": "DecryptResponse", 
    "RequestUuid": "ad74c84f-f696-47a8-a47b-bcdb77033b08"
}
```

