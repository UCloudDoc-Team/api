# 增加域名状态码防护规则-AddHTTPStatusDisguiseConf

增加域名状态码防护规则

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|	项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Name|string|规则名 对域名唯一|**Yes**|
|FullDomain|string|要操作的域名|**Yes**|
|StatusCode|int|需要防护的状态码, 取值范围401\~599|**Yes**|
|DisguiseManner|string|防护方式 过滤：Filter  伪装：Disguise|**Yes**|
|DisguiseFile|string|伪装文件，BASE64格式 Disguise时必选|No|
|MD5|string|伪装文件的MD5值，Disguise时必选|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Id|int|添加成功后返回的规则ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddHTTPStatusDisguiseConf
&Name=EXMszCNs
&FullDomain=egOcIqmH
&StatusCode=1
&DisguiseManner=HFVBeTut
&DisguiseFile=MrmqqCXj
&MD5=IHVUuMKC
&ProjectId=AeNofiWU
&RecordId=7
```

# Response Example
```
{
    "Action": "AddHTTPStatusDisguiseConfResponse", 
    "RetCode": 0, 
    "Id": 5
}
```

