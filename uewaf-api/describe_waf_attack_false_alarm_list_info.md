# 获取误报记录列表 - DescribeWafAttackFalseAlarmListInfo

## 简介

获取误报记录列表








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafAttackFalseAlarmListInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **Offset** | int | 记录 偏移，等效于PageNum |**Yes**|
| **Limit** | int | 记录限制数目，等效于PageSize |**Yes**|
| **Domain** | string | 要查询的域名，不填查询所有 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TotalCount** | int | 误报记录总数 |**Yes**|
| **DetailList** | array[[*WafAttack*](#WafAttack)] | 误报记录列表，参考WafAttack |**Yes**|

#### 数据模型


#### WafAttack

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 区域 |No|
| **Protocol** | string | 协议 |No|
| **ServerName** | string | 服务器名称 |No|
| **DestIp** | string | 目标IP地址 |No|
| **Port** | string | 端口 |No|
| **Alerts** | array[[*WafAlert*](#WafAlert)] | 告警匹配信息，参考WafAlert |No|
| **RequestHeaders** | [*RequestHeader*](#RequestHeader) | http请求头部信息，参考RequestHeader |No|
| **Attack** | string | 攻击类型 |No|
| **Method** | string | 请求方法 |No|
| **FalsePositive** | boolean | 是否误报 |No|
| **RiskRank** | string | 风险等级 |No|
| **TimeStamp** | int | 攻击时间戳 |No|
| **Host** | string | 主机名 |No|
| **Referer** | string | 引用地址 |No|
| **Count** | int | 攻击次数 |No|
| **Uri** | string | URI |No|
| **Client** | string | 客户端 |No|
| **Mode** | string | 工作模式 |No|
| **Action** | string | 匹配动作 |No|
| **UA** | string | 用户代理 |No|
| **ClientIPInfo** | [*CityInfo*](#CityInfo) | 客户端位置信息，参考CityInfo |No|
| **Args** | string | 参数 |No|

#### WafAlert

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Description** | string | 规则描述 |No|
| **Match** | object | 匹配规则 |No|
| **Id** | int | 匹配规则ID |No|

#### RequestHeader

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AcceptLanguage** | string | 接收语言类型 |No|
| **AcceptEncoding** | string | 支持编码类型 |No|
| **Host** | string | 主机 |No|
| **Accept** | string | 数据类型 |No|
| **UpgradeInsecureRequests** | string | http升级到https请求 |No|
| **Connection** | string | 连接方式 |No|
| **Cookie** | string | Cookie |No|
| **CacheControl** | string | 缓存行为 |No|
| **UserAgent** | string | 用户代理 |No|
| **XForwardFor** | string | XFF |No|

#### CityInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **CountryName** | string | 国家 |No|
| **RegionName** | string | 区域 |No|
| **CityName** | string | 城市 |No|
| **OwnerDomain** | string | 所属域名 |No|
| **Latitude** | string | 纬度 |No|
| **Longitude** | string | 经度 |No|
| **Timezone** | string | 时区 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafAttackFalseAlarmListInfo
&ProjectId=org-xxx
&Domain=www.test.com
&Offset=0
&Limit=10
```

### 响应示例
    
```json
{
  "Action": "DescribeWafAttackFalseAlarmListInfoResponse",
  "DetailList": [
    {
      "AccessId": "183.238.16.138-a9736253",
      "Action": "DENY",
      "Alerts": [
        {
          "Description": "XSS",
          "Id": 32003,
          "Match": {
            "0": "\u003cscript",
            "1": "\u003cscript",
            "2": "\u003c",
            "5": "script"
          }
        }
      ],
      "Args": "",
      "Attack": "xss",
      "Client": "183.238.16.138",
      "ClientIPInfo": {
        "city_name": "深圳",
        "country_name": "中国",
        "latitude": "22.547",
        "longitude": "114.085947",
        "owner_domain": "",
        "region_name": "广东",
        "timezone": "Asia/Shanghai"
      },
      "Count": 1,
      "DestIp": "106.75.79.224",
      "FalsePositive": true,
      "Host": "www.test.com",
      "Id": "5e8c1dbb243527db1df82677",
      "Method": "GET",
      "Mode": "SIMULATE",
      "Port": "80",
      "Protocol": "http",
      "Referer": "NULL",
      "Region": "cn-bj",
      "RequestBody": null,
      "RequestHeaders": {
        "Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8",
        "AcceptEncoding": "",
        "AcceptLanguage": "en-US",
        "CacheControl": "",
        "Connection": "",
        "Cookie": "",
        "Host": "www.test.com",
        "UpgradeInsecureRequests": "",
        "UserAgent": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; Tablet PC 2.0)",
        "XForwardFor": ""
      },
      "RiskRank": "high",
      "ServerName": "www.test.com",
      "TimeStamp": 1586240955,
      "TopId": 50146955,
      "UA": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; Tablet PC 2.0)",
      "Uri": "/home.html?user=\u0026password=\u0026action!login:cantLogin%3Cscript%3Ealert(1344)%3C/script%3E=AppScan"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





