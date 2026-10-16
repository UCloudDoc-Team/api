# 获取防火墙信息 - DescribeUEcFirewall

## 简介

获取防火墙信息









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeUEcFirewall`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **FirewallId** | string | 防火墙ID，默认为返回所有防火墙 |No|
| **ResourceId** | string | 绑定防火墙组的虚拟机资源ID |No|
| **Limit** | int | 返回数据长度，默认为20 |No|
| **Offset** | int | 列表起始位置偏移量，默认为0 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **FirewallSet** | array[[*FirewallInfo*](#FirewallInfo)] | 防火墙组详细信息，参见 FirewallInfo |No|
| **TotalCount** | int | 满足条件的节点总数 |No|

#### 数据模型


#### FirewallInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **FirewallId** | string | 防火墙Id |**Yes**|
| **Name** | string | 防火墙名称 |**Yes**|
| **CreateTime** | int | 创建时间 |**Yes**|
| **Rule** | array[[*RuleInfo*](#RuleInfo)] | 防火墙规则组，详情参见RuleInfo |**Yes**|
| **ResourceCount** | int | 防火墙绑定资源数量 |**Yes**|
| **Type** | string | 防火墙组类型，枚举值为： "user defined", 用户自定义防火墙； "recommend web", 默认Web防火墙； "recommend non web", 默认非Web防火墙 |**Yes**|
| **Remark** | string | 描述 |No|

#### RuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProtocolType** | string | 协议，可选值：TCP，UDP，ICMP |**Yes**|
| **Port** | string | 端口，范围用"-"符号分隔，如：1-65535 |**Yes**|
| **SrcIp** | string | 源ip |**Yes**|
| **Action** | string | ACCEPT（接受）和DROP（拒绝） |**Yes**|
| **Priority** | string | 优先级：HIGH（高），MEDIUM（中），LOW（低） |**Yes**|
| **Remark** | string | 备注 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeUEcFirewall
&ProjectId=IPGVCokh
&FirewallId=knaTcCxy
&ResourceId=gGkdCrrH
&Limit=3
&Offset=5
```

### 响应示例
    
```json
{
  "Action": "DescribeUEcFirewallResponse",
  "FirewallSet": [
    {
      "CreateTime": 4,
      "FirewallId": "DidupHCt",
      "Name": "tRQbcvcL",
      "Remark": "nrjnvwgW",
      "ResourceCount": 9,
      "Rule": [
        {
          "Action": "KIorAcnY",
          "Port": "QVwJuInC",
          "Priority": "mWhrOxCR",
          "ProtocolType": "pKlYpqvu",
          "Remark": "iYpwuoYc",
          "SrcIp": "VtNvFlyA"
        }
      ],
      "Type": "oQWGPWgi"
    }
  ],
  "RetCode": 0,
  "TotalCount": 9
}
```





