# 获取加速域名原始日志-GetUcdnDomainLog

获取加速域名原始日志

!> 注解：日志数据最长保留一周时间。

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DomainId.n|string|域名ID，创建加速域名时生成。默认全部域名|No|
|BeginTime|int|查询的起始时间，格式为Unix Timestamp。如果有EndTime，BeginTime必须赋值。|No|
|EndTime|int|查询的结束时间，格式为Unix Timestamp。EndTime默认为当前时间，BeginTime默认为当前时间前一天时间。|No|
|Type|int|查询粒度  0=default(没有粒度) 1=按小时  2=按天|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|LogSet|array|获取日志的连接地址。具体参考下面LogSetList|No|

## LogSetList
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Domain|string|域名|No|
|Logs|array|域名信息列表，参考LogSetInfo|No|

## LogSetInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Time|int|日志时间UnixTime|No|
|CnLog|array|国内日志url列表|No|
|AbroadLog|array|国外日志url列表|No|

# Request Example
```
http://api.ucloud.cn/?Action=GetUcdnDomainLog
&ProjectId=xxxxx
&DomainId.0=ucdn-xxx
&BeginTime=1399132800
&EndTime=1399132800
```

# Response Example
```
{
    "Action": "GetUcdnDomainLogResponse", 
    "LogSet": [
        {
            "Domain": "test_01.ucloud.cn", 
            "Logs": [
                {
                    "CnLog": [
                        "http://test_01.ucloud.cn/test_cn_01.log"
                    ], 
                    "AbroadLog": [
                        "http://test_01.ucloud.cn/test_abroad_01.log"
                    ], 
                    "Time": 1399132800
                }
            ]
        }, 
        {
            "Domain": "test_02.ucloud.cn", 
            "Logs": [
                {
                    "CnLog": [
                        "http://test_02.ucloud.cn/test_cn_01.log"
                    ], 
                    "AbroadLog": [
                        "http://test_02.ucloud.cn/test_abroad_01.log"
                    ], 
                    "Time": 1399132800
                }
            ]
        }
    ], 
    "RetCode": 0
}
```

