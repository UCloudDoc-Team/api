# 获取转发规则 - GetBGPServiceFwdRule

## 简介

获取转发规则






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetBGPServiceFwdRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetBGPServiceFwdRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源id  |**Yes**|
| **Offset** | int | 分页显示的起始偏移，默认值为0 |No|
| **Limit** | int | 分页显示的条目数，默认值为32 |No|
| **RuleIndex** | int | 查询指定的rule_id, 不填写则默认获取所有的转发规则 |No|
| **BgpIP** | string | 指定需要查询的IP下的规则 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **RuleCnt** | int | 满足要求的数据条目 |**Yes**|
| **RuleInfo** | array[[*BGPFwdRule*](#BGPFwdRule)] | 转发规则信息 |**Yes**|
| **AvailLoad** | int | 负载模式下可添加的规则数量（根据IP查询才返回此参数） |No|
| **AvailNonload** | int | 非负载模式下可添加的规则数量（根据IP查询才返回此参数） |No|
| **IpRuleExist** | boolean | 当前配置的规则中是否存在IP规则（根据IP查询才返回此参数） |No|

#### 数据模型


#### BGPFwdRule

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BgpIP** | string | 转发规则对应的BGP高防的IP |No|
| **RuleID** | string | 转发规则的ID |No|
| **CreateTime** | int | 创建时间，unix格式 |No|
| **UpdateTime** | int | 更新时间，unix格式 |No|
| **BgpIPPort** | int | 默认为0，为IP协议的转发端口，其余的自定义，在0\~65535范围内即可,但是同一IP下配置的规则端口不能重复 |No|
| **LoadBalance** | string | 转发协议的类型是否为负载均衡的：默认为“No”，还可以选择为“Yes”。负载模式的规则最多添加2条，非负载模式的规则最多添加8条 |No|
| **SourceDetect** | int | 表示对源站进行检测：默认为0表示关闭，还可以选择为1表示开启 |No|
| **BackupIP** | string | 备份源站的IP |No|
| **BackupPort** | int | 备份源站的端口 |No|
| **SourceInfo** | [*FwdSourceInfo*](#FwdSourceInfo) | 源站信息结构 |No|
| **ClientProxyInfo** | [*FwdClientProxyInfo*](#FwdClientProxyInfo) | 回源IP结构 |No|
| **RuleIndex** | int | 生成的规则的数据库索引值 |No|
| **Status** | string | 规则的状态 |No|
| **FwdType** | string | 配置的规则的转发类型 |No|
| **Remark** | string | 备注 |No|

#### FwdSourceInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Type** | string | 回源类型，分 IP 和 Domain |No|
| **Conf** | array[[*FwdSourceInfoConf*](#FwdSourceInfoConf)] | 回源配置列表 |No|

#### FwdClientProxyInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Count** | int | 回源IP个数 |No|
| **IPList** | array[string] | 回源IP列表 |No|

#### FwdSourceInfoConf

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Source** | string | 源站，兼容IP和域名 |No|
| **Port** | int | 源站端口 |No|
| **Toa** | int | 源站Toa |No|
| **IPList** | array[string] | 源站IP列表 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetBGPServiceFwdRule
&ResourceId="3327ebd4-5d8a-4aac-b1dc-31bbe20cd7d7"
&Offset=0
&Limit=10
&BgpIP="10.5.12.3"
&RuleIndex= 9759
```

### 响应示例
    
```json
{
  "Action": "GetBGPServiceFwdRuleResponse",
  "AvailLoad": 9,
  "AvailNonload": 49,
  "IpRuleExist": true,
  "RetCode": 0,
  "RuleCnt": 1,
  "RuleInfo": [
    {
      "BackupIP": "",
      "BackupPort": 0,
      "BgpIP": "10.5.12.3",
      "BgpIPPort": 0,
      "ClientProxyCount": 12,
      "ClientProxyIPList": "5.5.5.5,6.6.6.6,",
      "ClientProxyInfo": {
        "Count": 12,
        "IPList": [
          "5.5.5.5",
          "6.6.6.6"
        ]
      },
      "CreateTime": 1663828045,
      "FwdType": "IP",
      "LoadBalance": "Yes",
      "Remark": "",
      "RuleID": "ruleid-b639-464b-80d6-10.5.12.3",
      "RuleIndex": 9759,
      "SourceDetect": 0,
      "SourceIPInfo": "1.1.1.1,2.2.2.2",
      "SourceInfo": {
        "Conf": [
          {
            "IPList": [
              "1.1.1.1"
            ],
            "Port": 0,
            "Source": "1.1.1.1",
            "Toa": 200
          },
          {
            "IPList": [
              "2.2.2.2"
            ],
            "Port": 0,
            "Source": "2.2.2.2",
            "Toa": 200
          }
        ],
        "Type": "IP"
      },
      "SourcePort": "0,0",
      "Status": "Success",
      "ToaID": "200",
      "UpdateTime": 1663828047
    }
  ]
}
```





