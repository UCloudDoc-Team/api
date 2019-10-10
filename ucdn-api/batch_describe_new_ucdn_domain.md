# 批量获取加速域名配置-BatchDescribeNewUcdnDomain

批量获取加速域名配置

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|Offset|int|数据偏毅力昂，默认0，非负整数|No|
|Limit|int|返回数据长度，如果制定了Offset，则默认20，否则默认全部，非负整数|No|
|DomainId.n|string|域名id，创建域名时生成的id，默认获取账号下的所有域名信息，n为自然数|No|
|ChannelType|string|渠道ufile、uvideo|No|
|ChargeStatus|int|1-待测试，2-测试中，3-测试失败，4-测试过期，5-计费中|No|
|MonthChargeType|int|30-95带宽,31-日均峰值,32-第四峰值|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|满足条件的域名个数|No|
|MaxDomainNum|int|最大域名数量，默认20|No|
|ChargeType|string|当前计费方式，traffic代表按流量包计费，bandwidth按带宽付费，trafficused代表按流量后付费|No|
|LastChargeType|string|表示最后一次切换的计费方式，traffic代表按流量包计费，bandwidth按带宽付费，trafficused代表按流量后付费|No|
|Arrearage|bool|是否欠费，True-欠费，false-不欠费|No|
|Vip|string|vip标示，True-欠费，false-不欠费|No|
|DomainList|array||No|

## DomainInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Dn|string|域名|No|
|StartTime|int|开始时间|No|
|EndTime|int|结束时间|No|
|Period|int|年|No|
|Protect|string|隐私保护标志|No|
|TemplateId|string|模板id|No|
|IdType|string|证件类型|No|
|RegistrantType|string|注册人类型|No|
|AuditStatus|string|实名状态|No|
|DomainStatus|string|命名审核状态|No|
|Status|string|域名服务状态|No|
|Dns1|string|域名使用的dns|No|
|Dns2|string|域名使用的dns|No|
|Uname1|string|注册人所有人（中文）|No|
|Uname2|string|注册人所有人（英文）|No|
|Rname1|string| 注册人联系人（中文）|No|
|Rname2|string|注册人联系人（英文）|No|
|Uaddr1|string|注册人联系地址（中文）|No|
|Uaddr2|string|注册人联系地址（英文）|No|
|Ust|string|注册人国家（英文）|No|
|Uprov|string| 注册人省份（英文）|No|
|Ucity1|string|注册人城市（中文）|No|
|Ucity2|string|  注册人城市（英文）|No|
|Uzip|string|注册人邮编|No|
|Utelc|string|电话国家码|No|
|Utela|string|电话区号|No|
|Uteln|string|电话号码|No|
|Utele|string|电话分机|No|
|Ufaxc|string|传真国家码|No|
|Ufaxa|string|传真区号|No|
|Ufaxn|string|传真号码|No|
|Ufaxe|string|传真分机|No|
|Uemail|string|email|No|
|Aname1|string|联系所有人（中文）|No|
|Aname2|string|联系人所有人（英文）|No|
|Atelc|string|电话国家码|No|
|Atela|string|电话区号|No|
|Ateln|string|电话号码|No|
|Atele|string|电话分机|No|
|Afaxc|string|传真国家码|No|
|Afaxa|string|传真区号|No|
|Afaxn|string|传真号码|No|
|Afaxe|string|传真分机|No|
|Aemail|string|email|No|

# Request Example
```
https://api.ucloud.cn/?Action=BatchDescribeNewUcdnDomain
```

# Response Example
```
{
    "Action": "BatchDescribeNewUcdnDomainResponse", 
    "RetCode": 0
}
```

