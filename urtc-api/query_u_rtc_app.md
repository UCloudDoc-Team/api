# 查询app基本信息-QueryURtcApp

查询app基本信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|待查询app的appid(为空则是查询用户已创建的所有app或者不填此字段)|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|RetCode返回0则为succed,若不为0则为具体的错误提示内容|**Yes**|
|Data|array|返回的app基本信息列表|**Yes**|

## AppModel
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppName|string|app名称|**Yes**|
|AppId|string|appId|**Yes**|
|AppStatue|bool|app状态(true:启用，false:停用)|**Yes**|
|AppToken|string|apptoken(接入rtc鉴权使用，妥善保管)|**Yes**|
|AppCreatTime|string|app创建时间|**Yes**|
|Id|int|id序号|**Yes**|
|RecordStatue|string|录制是否开通(true:启用，false:停用)|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=QueryURtcApp
&AppId=fa3422b74ba211e9b10c00ff80725f6f
```

# Response Example
```
"{\n  \"Msg\": \"Succed\",\n  \"Data\": [\n    {\n      \"Id\":0,\n      \"AppName\": \"TNTsLSSR\",\n      \"AppId\": \"fa3422b74ba211e9b10c00ff80725f6f\",\n      \"AppStatue\": true,\n      \"AppToken\": \"uFgIVYnz\",\n      \"AppCreatTime\": \"2019-04-01 15:29:01\"\n    }\n  ],\n  \"RetCode\": 0,\n  \"Action\": \"QueryURtcAppResponse\"\n}"
```

