# 创建全球加速配置项-CreateUGAInstance

创建全球加速配置项

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID,如org-xxxx。请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|Name|string|加速实例名称|**Yes**|
|IPList|string|加速源IP，多个IP用逗号隔开(,)隔开;IPList和Domain二选一必填|No|
|Domain|string|加速源域名;IPList和Domain二选一必填|No|
|TCP.n|string|TCP端口号,已废弃。请使用 CreateUGAForwarder API 创建端口|No|
|UDP.n|string|UDP端口号，已废弃。请使用 CreateUGAForwarder API 创建端口|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UGAId|string|加速配置ID|**Yes**|
|CName|string|加速域名 用户可把业务域名CName到此域名上。注意：未绑定线路情况时 加速域名解析不出IP。|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUGAInstance
&Name=bFSqkBrw
&IPList=qdnZVXJy
&Domain=hgaRlvAw
&TaskSet=pZcYvksz
&HTTP.n=PlLOpzzS
&HTTPS.n=VcAmPHHP
&Location=EavleeXu
```

# Response Example
```
{
    "Action": "CreateUGAInstanceResponse", 
    "CName": "yfTztmrK", 
    "RetCode": 0, 
    "UGAAId": "qTjKMlcL"
}
```

