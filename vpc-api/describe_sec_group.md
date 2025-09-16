# 获取安全组信息 - DescribeSecGroup

## 简介








## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSecGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSecGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **Limit** | int | 分页查询数据长度。默认为20 |No|
| **Offset** | int | 分页查询起始位置偏移量。默认为0 |No|
| **VPCId** | string | 资源ID所属的 VPC ID |No|
| **SecGroupId.N** | string | 安全组资源 ID 数组，传入则 Offset/Limit/BusinessId 失效。支持数组格式。Type 为 string 数组。 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*SecGroupInfo*](#SecGroupInfo)] | 详见SecGroupInfo |**Yes**|

#### 数据模型


#### SecGroupInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecGroupId** | string | 安全组资源ID |No|
| **Name** | string | 安全组名称 |No|
| **VPCId** | string | VPC资源ID |No|
| **Account** | int | 用户 ID |No|
| **Tag** | string | 业务组 |No|
| **Remark** | string | 备注 |No|
| **Type** | string | 安全组类型，枚举值为： "user defined", 自定义创建安全组； "recommend web", 使用Web模板创建的安全组； "recommend non web", 使用非Web模板创建的安全组 |No|
| **CreateTime** | int | 创建的时间，格式为Unix Timestamp，如 1747030299 |No|
| **Rule** | array[[*SecGroupRuleInfo*](#SecGroupRuleInfo)] | 安全组组中的规则列表，参见 SecGroupRuleInfo |No|

#### SecGroupRuleInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RuleId** | string | 规则ID |No|
| **Direction** | string | "Ingress/Egress"，入站规则/出站规则 |No|
| **IPRange** | string | 地址 |No|
| **Priority** | int | 优先级 |No|
| **ProtocolType** | string | 协议类型 |No|
| **DstPort** | string | 目标端口 |No|
| **RuleAction** | string | 匹配策略 |No|
| **Remark** | string | 安全组规则备注 |No|
| **IPVersion** | string | IP 版本，如 "IPv4"。支持 IPv6 后废弃 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSecGroup
&Region=cn-zj
&ProjectId=pFHEwWhK
&SecGroupId.n=yswMXnnq
&Offset=MtvhXVlk
&Limit=MZYPwcOZ
&VPCId=ZJqpHNUF
&BusinessId=HNhpzbsv
```

### 响应示例
    
```json
{
  "Action": "DescribeSecGroupResponse",
  "DataSet": [
    "XJMgfJJa"
  ],
  "RetCode": 0
}
```





