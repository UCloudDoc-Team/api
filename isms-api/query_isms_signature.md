# 查询视频短信签名申请状态 - QueryISMSSignature

## 简介

调用接口QueryISMSSignature查询视频短信签名申请状态









## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `QueryISMSSignature`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |No|
| **SigId** | string | 已申请的短信签名ID（短信签名申请时的工单ID）；签名ID和签名至少需填写1项； |**Yes**|
| **SigContent** | string | 签名内容；签名ID和签名至少需填写1项； |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | [*OutSignature*](#OutSignature) | 签名信息，各字段说明详见OutSignature |**Yes**|

#### 数据模型


#### OutSignature

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SigId** | string | 短信签名ID |**Yes**|
| **SigContent** | string | 短信签名内容 |**Yes**|
| **Status** | int | 签名状态，0-待审核 1-审核中 2-审核通过 3-审核未通过 4-被禁用  |**Yes**|
| **ErrDesc** | string | 短信签名未通过审核原因 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=QueryISMSSignature
&ProjectId=pDaIibTX
&SigId=CIQfSZgu
&SigContent=DbGbAyow
```

### 响应示例
    
```json
{
  "Action": "QueryISMSSignatureResponse",
  "Data": {},
  "Message": "oTJxkngV",
  "RetCode": 0
}
```





