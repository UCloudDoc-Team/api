# 获取令牌信息-DescribeUFileToken

获取令牌信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|TokenId|string|令牌ID，只返回指定ID信息，否则拉取所有令牌|No|
|Display|int|0表示显示部分token信息；不传递和其他情况表示显示全部token信息|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|令牌描述信息|**Yes**|

## UFileTokenSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TokenId|string|令牌ID|**Yes**|
|TokenName|string|令牌名称|**Yes**|
|PublicKey|string|令牌公钥|**Yes**|
|PrivateKey|string|令牌私钥|**Yes**|
|AllowedOps|array|令牌允许执行的操作，[ TOKEN_ALLOW_NONE , TOKEN_ALLOW_READ , TOKEN_ALLOW_WRITE , TOKEN_ALLOW_DELETE , TOKEN_ALLOW_LIST, TOKEN_ALLOW_IOP , TOKEN_ALLOW_DP ]|**Yes**|
|AllowedPrefixes|array|令牌允许操作的key前缀|**Yes**|
|AllowedBuckets|array|令牌允许操作的bucket|**Yes**|
|ExpireTime|int|令牌的超时时间点|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|ModifyTime|int|修改时间|**Yes**|
|Region|string|所属地区|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUFileToken
&ProjectId=org-xxx
&TokenId=679c7e5e-74b8-4048-b622-33dd4e8634de
&Region=cn-bj
&Display=2
```

# Response Example
```
{
    "Action": "DescribeUFileTokenResponse", 
    "RetCode": 0, 
    "DataSet": [
        {
            "TokenId": "679c7e5e-74b8-4048-b622-33dd4e8634de", 
            "TolenName": "testname", 
            "AllowedPrefixes": [
                "test/test", 
                "test1/test1"
            ], 
            "PrivateKey": "7b01a354-adb2-49a1-9f68-af814e884c29", 
            "ExpireTime": 4102416000.0, 
            "PublicKey": "TOKEN_679c7e5e-74b8-4048-b622-33dd4e8634de", 
            "AllowedBuckets": [
                "bucket1", 
                "bucket2"
            ], 
            "AllowedOps": [
                "TOKEN_ALLOW_READ", 
                "TOKEN_ALLOW_WRITE"
            ]
        }, 
        {
            "TokenId": "679c7e5e-74b8-4048-b622-33dd4e8634dc", 
            "TokenName": "test1name", 
            "PrivateKey": "7b01a354-adb2-49a1-9f68-af814e884c27", 
            "AllowedPrefixes": [
                "test/test", 
                "test1/test1"
            ], 
            "ExpireTime": 4102416000.0, 
            "PublicKey": "TOKEN_679c7e5e-74b8-4048-b622-33dd4e8634dc", 
            "AllowedBuckets": [
                "bucket1", 
                "bucket2"
            ], 
            "AllowedOps": [
                "TOKEN_ALLOW_READ", 
                "TOKEN_ALLOW_WRITE"
            ]
        }
    ]
}
```

