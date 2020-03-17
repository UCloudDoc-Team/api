# 修改项目名称-ModifyURtcProjectName

修改项目的基本信息

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AppId|string|要修改的项目AppId|**Yes**|
|AppName|string|修改后的新项目名称（不能为空）|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AppId|string|修改的AppId|**Yes**|
|AppName|string|修改后的名称|**Yes**|
|Msg|string|RetCode返回0则为succed,若不为0则为具体的错误提示内容|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=ModifyURtcProjectName
&AppId=HcnYrWmv
&AppName=PuiNJbUw
```

# Response Example
```
{
    "Msg": "ZPoTUvOi", 
    "Action": "ModifyURtcProjectNameResponse", 
    "AppName": "lJbzNVWj", 
    "RetCode": 0, 
    "AppId": "zezMKcAL"
}
```

