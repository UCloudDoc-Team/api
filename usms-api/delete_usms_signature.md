# 删除短信签名-DeleteUSMSSignature

调用接口DeleteUSMSSignature删除短信签名

!> 1.不支持删除正在审核中的短信签名；2.短信签名删除后不可恢复，请谨慎操作。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|SigIds.N|int|签名ID（也即短信签名申请时的工单ID），支持以数组的方式，举例，以SigIds.0、SigIds.1...SigIds.N方式传入   |**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Message|string|返回状态码描述，如果操作成功，默认返回为空|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUSMSSignature
&ProjectId=org-bxxxxy
&SigIds.0=SIG20190XXX2C1844
&SigIds.1=SIG20190XXX3C1844
```

# Response Example
```
{
    "Action": "DeleteUSMSSignatureResponse", 
    "Message": "", 
    "RetCode": 0
}
```

