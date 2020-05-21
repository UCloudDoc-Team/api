# 获取指定域名的攻击行为概览 - DescribeWafAttackSummaryInfo

## 简介

获取指定域名的攻击行为概览








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafAttackSummaryInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **BeginTime** | int | 起始时间戳 |No|
| **FullDomain** | string | 域名，为空则查询所有域名 |No|
| **EndTime** | int | 截止时间戳 |No|
| **SearchType.N** | string | 统计类别数组，默认"attack,uri,client,riskrank" |No|
| **AttackType** | string | 攻击统计类型，查询 IP TOP10 时生效，默认全选；参数选项: protocol: 协议违规, xss: XSS攻击, sql: SQL注入, loopholes: 漏洞攻击, exec: 命令执行, webshell: WebShell上传, eaa: 越权访问, infoleak: 信息泄露, scan: 恶意扫描, cc: CC攻击, other: 其他 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*WafAttackSummaryInfo*](#WafAttackSummaryInfo) | 返回数据 |No|

#### 数据模型


#### WafAttackSummaryInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **AttackTypeDistribution** | array[string] | {AttackType: "cc", AttackName: "CC攻击", AttackCount: 9} |No|
| **RiskRankDistribution** | array[string] | {RiskRankType: "High", Priority: 0, AttackCount: 3} |No|
| **TimeAxisDistribution** | array[string] | {Time: 1564653600, AcceptCount: 0, DenyCount: 0} |No|
| **TopAttackIP** | array[string] | {SrcIp: "120.132.23.61", AttackCount: 3,IPDB:{}} |No|
| **TopAttackUri** | array[string] | {AttackUrl: "/test2", AttackCount: 7} |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafAttackSummaryInfo
&RecordId=org-xxx
&FullDomain=www.test.com
&TimeType=Hour
&AttackType=xss
```

### 响应示例
    
```json
{
  "JSON": {
    "Action": "DescribeWafAttackSummaryInfoResponse",
    "Data": {
      "AttackTypeDistribution": [
        {
          "AttackCount": 0,
          "AttackName": "XSS攻击",
          "AttackType": "xss"
        }
      ],
      "RiskRankDistribution": [
        {
          "AttackCount": 0,
          "Priority": 0,
          "RiskRankType": "High"
        },
        {
          "AttackCount": 0,
          "Priority": 1,
          "RiskRankType": "Middle"
        },
        {
          "AttackCount": 0,
          "Priority": 2,
          "RiskRankType": "Low"
        },
        {
          "AttackCount": 0,
          "Priority": 3,
          "RiskRankType": "Unknown"
        }
      ],
      "TimeAxisDistribution": [
        {
          "AcceptCount": 0,
          "DenyCount": 0,
          "Time": 1585883280
        },
        {
          "AcceptCount": 0,
          "DenyCount": 0,
          "Time": 1585883520
        }
      ],
      "TopAttackIP": [
        {
          "AttackCount": 3,
          "IPDB": {},
          "SrcIp": "120.132.23.61"
        }
      ],
      "TopAttackUri": [
        {
          "AttackCount": 7,
          "AttackUrl": "/test2"
        }
      ]
    },
    "RetCode": 0
  }
}
```





