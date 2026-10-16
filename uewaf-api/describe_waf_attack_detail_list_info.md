# 查询WAF攻击详情 - DescribeWafAttackDetailListInfo

## 简介

查询WAF攻击详情









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafAttackDetailListInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填表示默认项目 |No|
| **Offset** | int | 页面偏移 |**Yes**|
| **Limit** | int | 每页数量限制 |**Yes**|
| **TimeType** | string | 时间单位；可选项：Hour\|Day\|Week\|Month\|Custom；默认Hour |No|
| **AttackType.N** | string | 攻击类型["scan", "loopholes", "xss", "cc", "sql", "exec", "webshell", "infoleak", "eaa", "protocol", "other"] |No|
| **RiskRank.N** | string | 风险级别 |No|
| **ActionType.N** | string | 匹配动作，拦截、放行、告警 |No|
| **BeginTime** | int | 自定义开始时间戳 |No|
| **EndTime** | int | 自定义结束时间戳 |No|
| **FullDomain** | string | 要查询的域名，为空时查询所有 |No|
| **WafMode** | string | 工作模式：拦截ACTIVE\| 放行 INACTIVE\| 告警 SIMULATE |No|
| **SrcIP** | string | 来源IP |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DetailList** | array[[*WafAttack*](#WafAttack)] | 攻击详情列表，参考WafAttack |No|
| **TotalCount** | int | 攻击详情总数 |No|

#### 数据模型


#### WafAttack

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 区域 |No|
| **RequestHeaders** | string | 请求头部 |**Yes**|
| **RequestBody** | string | 请求body |**Yes**|
| **ClientPort** | string | 客户端端口 |**Yes**|
| **RequestID** | string | 请求uid |**Yes**|
| **ClientIPInfo** | [*CityInfo*](#CityInfo) | 源IP信息 |**Yes**|
| **Protocol** | string | 协议 |No|
| **ServerName** | string | 服务器名称 |No|
| **DestIp** | string | 目标IP地址 |No|
| **Port** | string | 端口 |No|
| **Alerts** | array[[*WafAlert*](#WafAlert)] | 告警匹配信息，参考WafAlert |No|
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
| **Args** | string | 参数 |No|
| **Id** | string |  |No|

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

#### WafAlert

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Match** | string | 命中内容 |**Yes**|
| **Description** | string | 规则描述 |No|
| **Id** | int | 匹配规则ID |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafAttackDetailListInfo
&ProjectId=org-xxx
&AttackType=xss
&RiskRank=high
&Domain=www.test.com
&Offset=0
&Limit=10
&TimeType=Hour
&WafMode=ATXLsRWf
&SrcIP=dLZPvjMa
```

### 响应示例
    
```json
{
  "Action": "DescribeWafAttackDetailListInfoResponse",
  "DetailList": [
    {
      "AccessId": "183.238.16.138-f97f82ee",
      "Action": "DENY",
      "Alerts": [
        {
          "Description": "XSS",
          "Id": 32003,
          "Match": {
            "0": "alert(",
            "14": "alert(",
            "34": "alert"
          }
        }
      ],
      "Args": "ctg=%22%20onmouseover=%22alert(1295)",
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
      "DestIp": "106.5.9.224",
      "FalsePositive": false,
      "Host": "www.test.com",
      "Id": "5e8c1db1243527db1df81bc2",
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
      "TimeStamp": 1586240945,
      "TopId": 0,
      "UA": "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0; Tablet PC 2.0)",
      "Uri": "/professor.php?ctg=%22%20onmouseover=%22alert(1295)"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





