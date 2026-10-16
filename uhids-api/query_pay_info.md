# 查询用户付费信息 - QueryPayInfo

## 简介

查询用户的付费信息，保护目前未消费点数，点数过期时间，自动续费开关等









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryPayInfo`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **BillPoint** | int | 未消费预付费点数 |**Yes**|
| **RemainTime** | string | 预付费点数剩余使用时长 |**Yes**|
| **ExpiratTime** | string | 预付费点数过期时间 |**Yes**|
| **AutoRenew** | boolean | 自动续费开关 |**Yes**|
| **AutoBusinessVer** | boolean | 自动企业版开关 |**Yes**|
| **RenewPointNum** | int | 用户最近一次购买的点数大小 |No|
| **CompanyId** | int | 公司ID |No|
| **OrganizationId** | int | 项目ID |No|
| **ResourceLongId** | string | 资源ID |No|
| **UpdateTime** | string | 更改时间 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryPayInfo
&ProjectId=pQAVszca
```

### 响应示例
    
```json
{
  "Action": "QueryPayInfoResponse",
  "AutoBusinessVer": false,
  "AutoRenew": true,
  "BillPoint": 5000000000000,
  "CompanyId": 5,
  "ExpiratTime": "HwrfnHxQ",
  "OrganizationId": 5,
  "RemainTime": "UnPTuuFs",
  "RenewPointNum": 2,
  "ResourceLongId": "QMINioPc",
  "RetCode": 0,
  "UpdateTime": "gJgdtqKU"
}
```





