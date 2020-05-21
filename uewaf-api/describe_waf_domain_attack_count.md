# 获取域名攻击次数 - DescribeWafDomainAttackCount

## 简介

获取域名当日攻击次数








## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafDomainAttackCount`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填为默认项目 |No|
| **FullDomain** | string | 域名，不填时查询该用户账号下所有域名的当日攻击数 |No|
| **BeginTime** | int | 查询开始时间，不填默认为最近1天 |No|
| **EndTime** | int | 查询结束时间 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **AttackCount** | int | 攻击次数 |**Yes**|
| **RequestCount** | int | 请求总数 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafDomainAttackCount
&ProjectId=org-xxx
&FullDomain=www.test.com
&BeginTime=1585885620
&EndTime=1585889920
```

### 响应示例
    
```json
{
  "Action": "DescribeWafDomainAttackCountRespose",
  "AttackCount": 2,
  "RequestCount": 15398,
  "RetCode": 0
}
```





