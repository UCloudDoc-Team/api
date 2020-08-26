# 查询用户访问日志 - DescribeWafAccessLog

## 简介

查询用户访问日志，最大支持10000条记录，最大支持7天内日志查询









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafAccessLog`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 域名 |**Yes**|
| **BeginTime** | int | 时间戳，默认为最近1小时 |No|
| **EndTime** | int | 时间戳，默认为最近1小时 |No|
| **RawQuery.N** | string | 查询字段，形式为 字段名:查询内容 ，模糊查询以斜杠包围内容，如 ：/test/  |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|
| **Limit** | int | 返回数据长度，最大100 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Res** | object | JSON数组 |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafAccessLog
&ProjectId=org-xxx
&FullDomain=www.test.com
&Begin=1585797198
&End=1585883598
&Offset=0
&Limit=1

```

### 响应示例
    
```json
{
  "Action": "qeuryAccessLogResponse",
  "Count": 2284,
  "Res": [
    {
      "@source": "106.75.185.203",
      "@timestamp": "2020-04-02T11:13:25+08:00",
      "_id": "5e8558889b75691004f4dc57",
      "bytes_sent": 469,
      "content_type": "",
      "cookies": "",
      "forward": "",
      "host": "www.test.com",
      "hostname": "gd-waf-2",
      "referer": "",
      "remote_addr": "106.75.151.54",
      "remote_port": 35594,
      "request_head": "HEAD / HTTP/1.1",
      "request_length": 78,
      "request_method": "HEAD",
      "request_time": 0.03,
      "request_uri": "/",
      "scheme": "http",
      "server_port": 80,
      "status": "302",
      "time_local": "2020-04-02T11:13:25+08:00",
      "top_id": 50146955,
      "upstream_addr": "152.32.170.130:80",
      "upstream_response_length": "0",
      "upstream_response_time": 0.03,
      "upstream_status": "302",
      "uri": "/",
      "user_agent": "UWAF Domain State Monitor"
    }
  ],
  "RetCode": 0
}
```





