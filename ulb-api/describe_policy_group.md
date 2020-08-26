# 获取内容转发组信息 - DescribePolicyGroup

## 简介

获取内容转发组详细信息






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribePolicyGroup)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribePolicyGroup`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |**Yes**|
| **GroupId** | string | 内容转发策略组ID |No|
| **Offset** | int | 数据偏移量，默认值为0 |No|
| **Limit** | int | 数据分页值，默认为20 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **DataSet** | array[[*UlbPolicyGroupSet*](#UlbPolicyGroupSet)] | 内容转发策略组列表，具体结构见 UlbPolicyGroupSet |No|

#### 数据模型


#### UlbPolicyGroupSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **GroupId** | string | 内容转发策略组ID |No|
| **GroupName** | string | 内容转发策略组名称 |No|
| **PolicySet** | array[[*UlbPolicySet*](#UlbPolicySet)] | 内容转发策略组详细信息，具体结构见 UlbPolicySet |No|

#### UlbPolicySet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **PolicyId** | string | 内容转发策略组ID |No|
| **Type** | string | 内容转发匹配字段的类型，当前只支持按域名转发。枚举值为： Domain，按域名转发 |No|
| **Match** | string | 内容转发匹配字段 |No|
| **VServerId** | string | 内容转发策略组ID应用的VServer实例的ID |No|
| **BackendSet** | array[[*UlbPolicyBackendSet*](#UlbPolicyBackendSet)] | 内容转发策略组ID所应用的后端资源列表，具体结构见 UlbPolicyBackendSet |No|

#### UlbPolicyBackendSet

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **BackendId** | string | 后端资源实例的ID |No|
| **PrivateIP** | string | 后端资源实例的内网IP |No|
| **Port** | int | 后端资源实例的服务端口 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribePolicyGroup
```

### 响应示例
    
```json
{
  "Action": "DescribePolicyGroupResponse",
  "DataSet": [
    {
      "GroupId": "ulb-fr-2axjbg",
      "GroupName": "new-policy",
      "PolicySet": [
        {
          "BackendSet": [
            {
              "BackendId": "1cf3c062-f551-48c7-a6e2-c2730d84303f",
              "Port": 80,
              "PrivateIP": "10.10.33.87"
            },
            {
              "BackendId": "a2ac0c73-1831-4379-b651-fbcb7702f6ec",
              "Port": 80,
              "PrivateIP": "10.10.32.101"
            },
            {
              "BackendId": "6277e964-83de-4548-b598-6b4d5a67a442",
              "Port": 80,
              "PrivateIP": "10.10.31.7"
            }
          ],
          "Match": "www.example.com",
          "PolicyId": "a3bfefc1-bfce-459c-baeb-2619f77cf0df",
          "Type": "Domain",
          "VServerId": "8aae44ba-f3fd-4162-9e32-2e64b89b646b"
        }
      ]
    },
    {
      "GroupId": "ulb-fr-dwkb5d",
      "GroupName": "eqeqeqeq",
      "PolicySet": []
    }
  ],
  "RetCode": 0,
  "TotalCount": 2
}
```





