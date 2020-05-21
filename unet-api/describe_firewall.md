# 获取防火墙信息 - DescribeFirewall

## 简介

获取防火墙组信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeFirewall)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeFirewall`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域 |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写 |No|
| **FWId** | string | 防火墙ID，默认为返回所有防火墙 |No|
| **ResourceType** | string | 绑定防火墙组的资源类型，默认为全部资源类型。枚举值为："unatgw"，NAT网关； "uhost"，云主机； "upm"，物理云主机； "hadoophost"，hadoop节点； "fortresshost"，堡垒机； "udhost"，私有专区主机；"udockhost"，容器；"dbaudit"，数据库审计. |No|
| **ResourceId** | string | 绑定防火墙组的资源ID |No|
| **Limit** | int | 返回数据长度，默认为20，最大10000000 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*FirewallDataSet*](#FirewallDataSet)] | 获取的防火墙组详细信息 参见 FirewallDataSet |No|

#### 数据模型


#### FirewallDataSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FWId** | string | 防火墙ID |**Yes**|
| **GroupId** | string | 安全组ID（即将废弃） |**Yes**|
| **Name** | string | 防火墙名称 |No|
| **Tag** | string | 防火墙业务组 |No|
| **Remark** | string | 防火墙备注 |No|
| **ResourceCount** | int | 防火墙绑定资源数量 |No|
| **CreateTime** | int | 防火墙组创建时间，格式为Unix Timestamp |No|
| **Type** | string | 防火墙组类型，枚举值为： "user defined", 用户自定义防火墙； "recommend web", 默认Web防火墙； "recommend non web", 默认非Web防火墙 |No|
| **Rule** | array[[*FirewallRuleSet*](#FirewallRuleSet)] | 防火墙组中的规则列表，参见 FirewallRuleSet |No|

#### FirewallRuleSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SrcIP** | string | 源地址 |No|
| **Priority** | string | 优先级 |No|
| **ProtocolType** | string | 协议类型 |No|
| **DstPort** | string | 目标端口 |No|
| **RuleAction** | string | 防火墙动作 |No|
| **Remark** | string | 防火墙规则备注 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeFirewall
&Region=cn-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeFirewallResponse",
  "DataSet": [
    {
      "CreateTime": 1508472648,
      "FWId": "firewall-XXXX",
      "GroupId": "25575",
      "Name": "非Web服务器推荐(22，3389)",
      "Remark": "开放22，3389端口和ICMP",
      "ResourceCount": 0,
      "Rule": [
        {
          "DstPort": "22",
          "Priority": "HIGH",
          "ProtocolType": "TCP",
          "RuleAction": "ACCEPT",
          "SrcIP": "0.0.0.0/0"
        },
        {
          "DstPort": "3389",
          "Priority": "HIGH",
          "ProtocolType": "TCP",
          "RuleAction": "ACCEPT",
          "SrcIP": "0.0.0.0/0"
        },
        {
          "DstPort": "",
          "Priority": "HIGH",
          "ProtocolType": "ICMP",
          "RuleAction": "ACCEPT",
          "SrcIP": "0.0.0.0/0"
        }
      ],
      "Tag": "Default",
      "Type": "recommend non web"
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





