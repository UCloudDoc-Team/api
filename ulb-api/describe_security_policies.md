# 获取安全策略的信息 - DescribeSecurityPolicies

## 简介

获取安全策略的信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeSecurityPolicies)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeSecurityPolicies`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist) |**Yes**|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **SecurityPolicyId** | string | 安全策略ID |No|
| **Limit** | int | 数据分页值 |No|
| **Offset** | int | 数据偏移量 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*SecurityPolicy*](#SecurityPolicy)] | 	<br />安全策略列表，每项参数详见SecurityPolicy |No|
| **TotalCount** | int | 满足条件的安全策略总数 |No|

#### 数据模型


#### SecurityPolicy

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SecurityPolicyId** | string | 安全策略ID |**Yes**|
| **SecurityPolicyName** | string | 安全策略名称 |**Yes**|
| **TLSVersion** | string | TLS最低版本 |**Yes**|
| **SSLCiphers** | array[string] | 加密套件 |**Yes**|
| **SecurityPolicyType** | int | 安全策略类型 0：预定义 1：自定义 |**Yes**|
| **VServerSet** | array[[*BindVServerInfo*](#BindVServerInfo)] | 关联的监听 |**Yes**|

#### BindVServerInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **VServerId** | string | 绑定的VServerId |**Yes**|
| **VServerName** | string | 绑定的VServer名称 |**Yes**|
| **Port** | int | VServer端口 |**Yes**|
| **ULBId** | string | ULB的ID |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeSecurityPolicies
&Region=cn-bj2
&ProjectId=project-XXXXX
&SecurityPolicyId=security-XXXXX
&Limit=2
&Offset=8
```

### 响应示例
    
```json
{
  "Action": "DescribeSecurityPoliciesResponse",
  "DataSet": [
    {
      "SSLCiphers": [
        "ECDHE-ECDSA-AES128-SHA256"
      ],
      "SecurityPolicyId": "security-XXXXX",
      "SecurityPolicyName": "new-security",
      "SecurityPolicyType": 1,
      "TLSVersion": "TLSv1.2",
      "VServerSet": [
        {
          "Port": 443,
          "ULBId": "ulb-XXXXX",
          "VServerId": "vserver-XXXXX",
          "VServerName": "443"
        }
      ]
    }
  ],
  "RetCode": 0,
  "TotalCount": 1
}
```





