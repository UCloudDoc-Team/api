# 获取用户购买详细信息 - DescribeWafUserTransactionInfo

## 简介

获取用户购买的详细信息，包括资源ID，版本类型，过期时间，付费方式，购买价格









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `DescribeWafUserTransactionInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TransactionInfo** | [*TransactionInfo*](#TransactionInfo) | 用户购买服务的详细信息，参考TransactionInfo |**Yes**|

#### 数据模型


#### TransactionInfo

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ResourceId** | string | 资源ID |No|
| **Editon** | string | 版本类型 |No|
| **ExpireTime** | string | 服务到期时间 |No|
| **ChargeType** | string | 付费类型 |No|
| **Price** | float | 购买价格，单位：元，精确到分 |No|
| **TransactionId** | int | 资源的唯一索引 |No|
| **TransactionNo** | string | 资源订单号 |No|
| **HasWaf** | boolean | 是否购买了WAF |No|
| **Expired** | string | 是否已过期，有此字段即为已过期 |No|
| **WorkRegions** | string | 部署区域 |No|
| **Serving** | string | 服务是否生效中 |No|
| **LogStorage** | int | 是否开启日志扩展包 |No|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=DescribeWafUserTransactionInfo
&ProjectId=org-xxx
```

### 响应示例
    
```json
{
  "Action": "DescribeWafUserTransactionInfoResponse",
  "RetCode": 0,
  "TransactionInfo": {
    "ChargeType": "Month",
    "CreateTime": "2017-04-10 13:30:05",
    "Editon": "Professional",
    "ExpireTime": "2020-06-03 00:00:00",
    "Expired": "",
    "HasWaf": true,
    "LogStorage": 0,
    "ResourceId": "usecure_uewaf-lbjszn",
    "Serving": "Y",
    "TransactionId": 31,
    "TransactionNo": "20170410050160160645159",
    "WorkRegions": "cn-gd,cn-sh,hk,cn-bj,tw-tp,us-ca,kr-seoul,jpn-tky",
    "WorkZone": "mainland"
  }
}
```





