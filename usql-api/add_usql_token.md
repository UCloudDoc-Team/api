# 增加授权-AddUSQLToken

为USQL增加访问其他UCloud产品的授权Token

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|用户项目ID， 用户不填则为默认项目|No|
|DataSource|string|数据源类型， 如UFile|**Yes**|
|AccessKeyId|string|令牌密钥对中的公钥|**Yes**|
|AccessKeySecret|string|令牌密钥对中的私钥|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Region|string|服务区域|No|
|DataSource|string|令牌对应的数据源名称， 如ufile|No|

# Request Example
```
https://api.ucloud.cn/?Action=AddUSQLToken
&Region=xxx
&ProjectId=SgZsaQGG
&DataSourceType=UFile
&AccessKeyId=xxxxx
&AccessKeySecret=yyyyy

```

# Response Example
```
{
    "Action": "AddUSQLTokenResponse", 
    "Region": "xxx", 
    "RetCode": 0, 
    "DataSource": "ufile"
}
```

