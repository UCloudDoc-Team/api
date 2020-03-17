# 创建APP-CreateUrtcApp

创建项目app(返回项目id)

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppName|string|创建的APP名称（不能为空）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|返回消息内容（成功succed,错误码不为0时，为具体提示内容）|**Yes**|
|Data|object|创建成功后返回的app基本信息（参数见CreatAppModel）|**Yes**|

## CreatAppModel
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppName|string|app名称|**Yes**|
|AppId|string|appId|**Yes**|
|AppStatue|bool|app状态(true:启用，false:停用)|**Yes**|
|AppToken|string|apptoken(接入rtc鉴权使用，妥善保管)|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUrtcApp
&AppName=qElRnmFQ
```

# Response Example
```
{
    "Msg": "Succed", 
    "Action": "CreateUrtcAppResponse", 
    "Data": {
        "AppStatue": true, 
        "AppToken": "fa3422b74ba211e9b10c00ff80725f6f", 
        "AppId": "77d17d2f3f2b11e9b9ba00ff80725f6f", 
        "AppName": "qElRnmFQ"
    }, 
    "RetCode": 0
}
```

