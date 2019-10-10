# 更新令牌-UpdateUFileToken

更新令牌的操作权限，可操作key的前缀，可操作bucket和令牌超时时间点

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|TokenId|string|令牌ID|**Yes**|
|TokenName|string|令牌名称|No|
|AllowedOps.n|string|令牌允许执行的操作，[ TOKEN_ALLOW_NONE , TOKEN_ALLOW_READ , TOKEN_ALLOW_WRITE , TOKEN_ALLOW_DELETE , TOKEN_ALLOW_LIST, TOKEN_ALLOW_IOP , TOKEN_ALLOW_DP ]|No|
|AllowedPrefixes.n|string|令牌允许操作的key前缀|No|
|AllowedBuckets.n|string|令牌允许操作的bucket|No|
|ExpireTime|int|令牌的超时时间点（时间戳）;注意：过期时间不能超过 4102416000|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=UpdateUFileToken
&ProjectId=org-xxx
&Region=cn-bj
&TokenId=679c7e5e-74b8-4048-b622-33dd4e8634db
&TokenName=testname
&AllowedOps.0=TOKEN_ALLOW_READ 
&AllowedOps.1=TOKEN_ALLOW_WRITE
&AllowedPrefixes.0=test/test
&AllowedPrefixes.1=test1/test1
&AllowedPrefixes.2=test2/test2
&AllowedBuckets.0=bucket0
&AllowedBuckets.1=bucket1
&ExpireTime=1520411979
```

# Response Example
```
{
    "Action": "UpdateUFileTokenResponse", 
    "RetCode": 0
}
```

