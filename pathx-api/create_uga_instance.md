# 创建全球加速配置项-CreateUGAInstance

创建全球加速配置项

```
加速配置创建完毕后 需要调用UGABindUPath接口才能使用
```

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](api/summary/get_project_list)|**Yes**|
|Name|string|加速配置实例名称|**Yes**|
|IPList|string|加速源IP，多个IP用英文半角逗号(,)隔开；IPList和Domain二选一必填|No|
|Domain|string|加速源域名，IPList和Domain二选一必填|No|
|TCP.n|string|TCP端口号，已废弃。请使用 CreateUGAForwarder API 创建端口|No|
|UDP.n|string|UDP端口号，已废弃。请使用 CreateUGAForwarder API 创建端口|No|

```
UGA作为加速配置实例，计费周期跟随绑定的UPath资源，资源到期自动续费，账户余额不足会产生欠费订单 直到资源被回收。如果没有绑定线路，加速配置不收取任何费用。
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UGAId|string|加速配置ID|**Yes**|
|CName|string|加速域名 用户可把业务域名CName到此域名上。注意：未绑定线路情况时 加速域名解析不出IP。|No|
|Message|string|返回信息|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUGAInstance
&Name=test
&Domain=google.com
```

# Response Example
```
{
    "Action": "CreateUGAInstanceResponse", 
    "Message": "", 
    "CName": "xxx.ucloudgda.com", 
    "RetCode": 0, 
    "UGAId": "uga-xxxx"
}
```

