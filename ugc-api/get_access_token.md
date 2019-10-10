# 获取授权Token-GetAccessToken

提交任务接口使用AccessToken做身份验证，此接口用于获取AccessToken。

```
关于AccessToken的说明： AccessToken的有效期为ExpireIn来传达，默认为7200秒，为了保证调用安全，建议不要设置过长的有效期。 用户需要根据有效时间提前去刷新AccessToken。刷新后及旧Token过期前新老AccessToken都可用，保证业务的平滑过渡。
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ExpireIn|int|Token有效时间，默认为7200秒|No|
|GrantType|string|默认为Task|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AccessToken|string|授权Token|No|
|ExpireIn|int|Token有效时间|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetAccessToken
&Region=cn-bj2
```

# Response Example
```
{
    "Action": "GetAccessTokenResponse", 
    "Message": "", 
    "ExpireIn": 7200, 
    "RetCode": 0, 
    "AccessToken": "H2JKDKOW3HN24CGG1PV3DV779932C"
}
```

