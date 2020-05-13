# 获取短信发送状态 - GetUSMSSendReceipt

## 简介

调用接口GetUSMSSendReceipt短信发送状态信息

?> 短信提交发送后，可调用接口GetUSMSSendReceipt查询及获取短信发送的状态信息；若发送后未立即拿到回执状态，建议在发送后5至10分钟内在尝试代用获取，若超过12小时仍未拿到发送状态，可联系UCloud技术支持协助



## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK（[Python](https://github.com/ucloud/ucloud-sdk-python3) / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Java](https://github.com/ucloud/ucloud-sdk-java)）
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=GetUSMSSendReceipt)
- [工作流引擎 StepFlow](https://console.ucloud.cn/stepflow/manage/)

## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `GetUSMSSendReceipt`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Region** | string | 地域。 参见 [地域和可用区列表](api/summary/regionlist) |No|
| **Zone** | string | 可用区。参见 [可用区列表](api/summary/regionlist) |No|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) |No|
| **SessionNoSet.N** | string | 发送短信时返回的SessionNo集合，SessionNoSet.0,SessionNoSet.1....格式 |**Yes**|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **Data** | array[[*ReceiptPerSession*](#ReceiptPerSession)] | 回执信息集合 |**Yes**|

#### 数据模型


#### ReceiptPerSession

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **SessionNo** | string | 发送短信时返回的SessionNo |**Yes**|
| **ReceiptSet** | array[[*ReceiptPerPhone*](#ReceiptPerPhone)] | 每个手机号的短信回执信息集合 |**Yes**|

#### ReceiptPerPhone

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Phone** | string | 手机号码 |**Yes**|
| **CostCount** | int | 消耗短信条数 |**Yes**|
| **ReceiptResult** | string | 回执结果 |**Yes**|
| **ReceiptDesc** | string | 回执结果描述 |**Yes**|
| **ReceiptTime** | int | 回执返回时间 |**Yes**|

## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=GetUSMSSendReceipt
&ProjectId=org-XXXXqi
&SessionNoSet.0=497XXXX4-eXXXXc-4XXX
```

### 响应示例
    
```json
{
  "Action": "GetUSMSSendReceiptResponse",
  "Data": [
    {
      "ReceiptSet": [
        {
          "CostCount": 1,
          "Phone": "185XXX9057",
          "ReceiptCode": "",
          "ReceiptDesc": "Successfully delivered to target phone",
          "ReceiptResult": "Success",
          "ReceiptTime": 1554168750
        }
      ],
      "SessionNo": "497XXXX4-eXXXXc-4XXX"
    }
  ],
  "Message": "Action success",
  "RetCode": 0
}
```





