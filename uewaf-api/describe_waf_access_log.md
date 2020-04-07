# 查询用户访问日志-DescribeWafAccessLog

查询用户访问日志，最大支持10000条记录，最大支持7天内日志查询

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FullDomain|string|域名|**Yes**|
|BeginTime|int|时间戳，默认为最近1小时|No|
|EndTime|int|时间戳，默认为最近1小时|No|
|RawQuery.n|string|查询字段，形式为 字段名:查询内容 ，模糊查询以斜杠包围内容，如 ：/test/ |No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，最大100|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Res|object|JSON数组|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeWafAccessLog
&ProjectId=org-xxx
&FullDomain=www.test.com
&Begin=1585797198
&End=1585883598
&Offset=0
&Limit=1

```

# Response Example
```
{
    "Action": "qeuryAccessLogResponse", 
    "Count": 2284, 
    "RetCode": 0, 
    "Res": [
        {
            "status": "302", 
            "cookies": "", 
            "upstream_status": "302", 
            "@timestamp": "2020-04-02T11:13:25+08:00", 
            "uri": "/", 
            "request_time": 0.03, 
            "remote_addr": "106.75.151.54", 
            "hostname": "gd-waf-2", 
            "request_method": "HEAD", 
            "server_port": 80, 
            "forward": "", 
            "scheme": "http", 
            "request_head": "HEAD / HTTP/1.1", 
            "request_length": 78, 
            "upstream_response_length": "0", 
            "host": "www.test.com", 
            "referer": "", 
            "content_type": "", 
            "request_uri": "/", 
            "remote_port": 35594, 
            "bytes_sent": 469, 
            "top_id": 50146955, 
            "@source": "106.75.185.203", 
            "user_agent": "UWAF Domain State Monitor", 
            "upstream_response_time": 0.03, 
            "time_local": "2020-04-02T11:13:25+08:00", 
            "upstream_addr": "152.32.170.130:80", 
            "_id": "5e8558889b75691004f4dc57"
        }
    ]
}
```

