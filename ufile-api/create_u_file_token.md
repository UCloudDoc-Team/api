# 创建UFile令牌-CreateUFileToken

创建ufile令牌

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|TokenName|string|令牌名称|**Yes**|
|AllowedOps.n|string|令牌允许执行的操作，[ TOKEN_ALLOW_NONE , TOKEN_ALLOW_READ , TOKEN_ALLOW_WRITE , TOKEN_ALLOW_DELETE , TOKEN_ALLOW_LIST, TOKEN_ALLOW_IOP , TOKEN_ALLOW_DP  ]。默认TOKEN_ALLOW_NONE|No|
|AllowedPrefixes.n|string|令牌允许操作的key前缀，默认*表示全部|No|
|AllowedBuckets.n|string|令牌允许操作的bucket，默认*表示全部|No|
|ExpireTime|int|令牌的超时时间点（时间戳），默认一天；注意：过期时间不能超过 4102416000|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TokenId|string|创建令牌的token_id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUFileToken
&ProjectId=org-xxx
&Region=cn-bj
&TokenName=testname
&AllowedOps.0=TOKEN_ALLOW_WRITE
&AllowedOps.1=TOKEN_ALLOW_READ 
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
    "Action": "CreateUFileTokenResponse", 
    "RetCode": 0, 
    "TokenId": "xUoZJgIz"
}
```

