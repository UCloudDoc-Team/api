# 启用或者关停APP-EnableURtcApp

启用或者关停指定的APP

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|要关停的项目Appid|**Yes**|
|AppEnable|bool|是否启用App（true:启用，false:停用）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Msg|string|返回码不为0时具体的错误消息，为0时为succed|**Yes**|
|Data|object|改变状态成功时返回具体的appid和当前状态（参见EnableAppModel）|No|

## EnableAppModel
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|appId|**Yes**|
|AppStatue|bool|项目状态|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=EnableURtcApp
&AppId=urtc-z4r1txxy
&AppEnable=false
```

# Response Example
```
{
    "Msg": "Succed", 
    "Action": "EnableURtcAppResponse", 
    "Data": {
        "AppStatue": false, 
        "AppId": "urtc-z4r1txxy"
    }, 
    "RetCode": 0
}
```

