# 获取基于NAT创建的内外网IP映射规则信息 - DescribeSnatDnatRule

## 简介

获取基于NAT创建的内外网IP映射规则信息

?> PrivateIp、NATGW同时仅允许一个参数有值




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSnatDnatRule)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSnatDnatRule`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **NATGWId.N** | string | 获取NAT上添加的所有SnatDnatRule信息 |No|
| **EIP.N** | string | 获取EIP对应的SnatDnatRule信息 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*SnatDnatRuleInfo*](#SnatDnatRuleInfo)] | 规则信息 |No|

#### 数据模型


#### SnatDnatRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PrivateIp** | string | 内网IP地址 |No|
| **NATGWId** | string | 映射所使用的NAT网关资源ID |No|
| **EIP** | string | EIP的IP地址 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSnatDnatRule
&Region=cn-zj
&ProjectId=QRbWkHUb
&NATGWId=cDLnarQV
&Offset=kbFtTKlH
&Limit=GMKqQMhV
&PrivateIp.n=NbnLFMsf
&EIPAddr.n=eWlihxoN
&RuleId.n=kHylfauB
&PrivateIp.n=hpZCJtGP
&EIPAddr.n=zQgqwHES
&RuleId.n=mXPVWbPY
```

### 响应示例
    
```json
{
  "Action": "DescribeSnatDnatRuleResponse",
  "NATGWMapInfos": "qIQkNLMg",
  "RetCode": 0
}
```





