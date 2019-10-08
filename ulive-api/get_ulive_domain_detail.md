# 获取直播加速域名信息列表-GetUliveDomainDetail

获取直播加速域名信息列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|DomainId.n|string|创建域名时候生成的domain_uid 可以传递多个，n代表自然数|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的直播加速个数|**Yes**|
|ChargeType|string|表示当前的计费方式，traffic代表按流量包计费，bandwidth按带宽付费|**Yes**|
|LastChargeType|string|表示最后一次切换的计费方式，traffic代表按流量包计费，bandwidth按带宽付费|**Yes**|
|Arrearage|array|是否欠费，1-国内流量欠费 2-国外流量欠费 3-国内日带宽欠费 4-国外日带宽欠费 (线下按月带宽不需要)|No|
|DomainSet|array|获取的域名信息，具体参考下面DomainSet|No|

## DomainSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DomainId|string|域名Id，创建直播加速生成的Id|**Yes**|
|LiveName|string|直播加速名称|**Yes**|
|PublishDomain|string|推流域名(拉流加速时，该字段为空)|**Yes**|
|PublishCname|string|推流Cname域名，客户推流域名需要CNAME到该域名(拉流加速时，该字段为空)|**Yes**|
|AccessPoint|string|接入点|**Yes**|
|CreatTime|int|创建时间，格式：unix时间戳|**Yes**|
|DomainInfoSet|array|播放域名信息列表，参考DomainInfoSet|**Yes**|
|Status|string|加速状态。checking：配置中；enabled：加速中；failed：失败；deleting：删除中；disabling：禁用中；disabled：禁用|No|
|SourceIp|string|源站域名或ip，如不为空，则为拉流域名；如为空则为推流域名|No|
|RecordStatus|string|录制状态。disabled:未开启；checking：配置中；enabled：已开启；deleting：关闭中；unsupported：不支持|No|
|RecordBucket|string|存储录制文件的bucket名称。|No|
|RecordCallbackUrl|string|用户的录制回调url地址。|No|

## DomainInfoSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Domain|string|域名|**Yes**|
|Cname|string|CDN域名，客户CNAME到该域名播放|**Yes**|
|Type|string|播放域名支持协议类型 rtmp/hdl、hls|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=GetUliveDomainDetail
&DomainId.n=xqYIinOu
```

# Response Example
```
{
    "RetCode": 0, 
    "TotalCount": 8, 
    "LastChargeType": "ZlMoxGrC", 
    "DomainSet": [
        "ZfbjgMWv", 
        "nnKsANmn", 
        "wPcPheHq", 
        "rzePRDUB", 
        "UFhagnrX", 
        "uQPKqAFF"
    ], 
    "ChargeType": "qEDKEeUf", 
    "Action": "GetUliveDomainDetailResponse", 
    "Arrearage": [
        7, 
        7, 
        5
    ]
}
```

