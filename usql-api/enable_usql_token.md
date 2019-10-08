# 设置USQL授权的状态-EnableUSQLToken

用户可以开启/关闭其他产品为USQL开通的授权

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID， 不填则为默认项目|No|
|DataSource|string|数据源类型，如ufile|**Yes**|
|State|int|0: 关闭， 1: 开启|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Request|string|API请求ID|No|
|DataSourceType|string|数据源名称， 如ufile|No|
|Enable|bool|true： 该授权已经启用false: 该授权已经关闭|No|

# Request Example
```
https://api.ucloud.cn/?Action=EnableUSQLToken
&Region=xxx
&ProjectId=mDwzQJik
&DataSourceType=ufile
&State=1
&DataSource=UxRYTgTY
```

# Response Example
```
{
    "Action": "EnableUSQLTokenResponse", 
    "DataSourceType": "ufile", 
    "Enable": true, 
    "Request": "177fcc1e-19ae-403c-9832-c1f970b28877", 
    "RetCode": 0
}
```

