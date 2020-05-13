# 查询自动添加黑名单策略 - DescribeAutoWafDomainBlackList

## 简介

查询自动添加黑名单策略





## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=DescribeAutoWafDomainBlackList)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeAutoWafDomainBlackList`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **FullDomain** | string | 域名 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Rows** | array[[*AutoWafDomainBlackList*](#AutoWafDomainBlackList)] | 自动拦截策略列表，参考AutoWafDomainBlackList |No|
| **TotalCount** | int | 自动拦截策略数量 |No|

#### 数据模型


#### AutoWafDomainBlackList

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Id** | int | 规则ID |**Yes**|
| **FullName** | string | 规则所属域名 |**Yes**|
| **AttackType** | string | 攻击类型 |**Yes**|
| **ActionType** | string | 防御模式 |**Yes**|
| **AttackCount** | int | 攻击数量 |**Yes**|
| **IntervalTime** | int | 攻击统计区间，单位:秒 |**Yes**|
| **ExpiredTime** | int | 攻击过期区间，单位:秒 |**Yes**|
| **Enable** | int | 启用状态;1表示启用,0表示禁用 |**Yes**|
| **CreateTime** | string | 创建时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeAutoWafDomainBlackList
&ProjectId=org-xxx
&FullDomain=www.test.com
```

### 响应示例
    
```json
{
  "Action": "DescribeAutoWafDomainBlackListResponse",
  "RetCode": 0,
  "Rows": [
    {
      "ActionType": "forbidden",
      "AttackCount": 10,
      "AttackType": "all",
      "CreateTime": 1585192039,
      "Enable": 1,
      "ExpireTime": 60,
      "FullDomain": "www.test.com",
      "Id": 591,
      "IntervalTime": 60
    },
    {
      "ActionType": "forbidden",
      "AttackCount": 10,
      "AttackType": "protocol",
      "CreateTime": 1585878780,
      "Enable": 1,
      "ExpireTime": 60,
      "FullDomain": "www.test.com",
      "Id": 603,
      "IntervalTime": 60
    }
  ],
  "TotalCount": 2
}
```





